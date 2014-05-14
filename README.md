# marionette-upgrade-why

The v2 CHANGELOG is meant to be a succinct description of each change made for v2. But
that is only so helpful. A description of a change without much explanation leaves one
with the big question: "Why?" And that's the very question the Marionette Upgrade Why
is meant to answer.

To begin, select a v2 change from the menu below.

### v2 Changelog

#### General

- Removed the `Marionette.$` proxy. We are now using `Backbone.$` instead.

- triggerMethod now calls `on`MethodName before triggering the event. Previously it was the other way around.

- Stricter JSHint rules were implemented for more consistent style across the codebase.

- A new property, `Marionette.VERSION`, was added.

- All instances of the word `type` in the API have been replaced with the word `class`. For instance:
  - regionType => regionClass
  - ChildViewType => ChildViewClass

- Most classes now have `getOption` attached to their instance, taking advantage of the new helper function `Marionette.proxyGetOption`

- Most classes now have `bindEntityEvents` attached to their instance, taking advantage of the new helper function `Marionette.proxyBindEntityEvents`

- Most classes now have `unbindEntityEvents` attached to their instance, taking advantage of the new helper function `Marionette.proxyUnbindEntityEvents`

- The built version of Marionette comes in a UMD wrapper. 

#### Applications and Modules

- The arguments of a Module’s initialize function are now consistent with Module constructor argument order. Previously they were inconsistent with one another.
```js
initialize: function( moduleName, app, options ) {
```

- Application’s `initialize` triggerMethods have been renamed to `start`, which is more descriptive of what is actually happening. More specifically, `initialize:before` and `initialize:after` are now `before:start` and `start`, respectively. No functionality has been lost with this change.

- The Application message system has been replaced with a [channel named “global”](https://github.com/marionettejs/backbone.wreqr#channel)

- Applications have two new triggerMethods: `before:region:add` and `before:region:remove` to complement their existing region events.

#### Controllers

- `stopListening` is now called after the `destroy` triggerMethod is called.

#### Behaviors

- `Behaviors` now support a means to group behaviors together. Any Behavior can now have a behavior key of its own, very similar to how a view can have behaviors.

#### Regions

- Regions now throw an error when they are instantiated with a nonexistent el. Previously this was a silent failure.

- Regions now use `.innerHtml` when clearing contents as compared this `this.$el.empty()`.

- `region.show` now return `this`, just like how a view’s render returns `this`.

- Regions trigger two new events, `before:swap` and `swap`, when it swaps views when calling `show`.

- Region’s el can now be a DOM node / DOM string selector / Jquery selector instance, just like a View’s el.

- Regions now expose region.el and region.$el, just like View’s.
Due to this change if you were depending on region.el to be a string selector you must update your code to use region.$el.selector. 

- Calling show on a region with the same view that is currently shown is now a noop. Previously the view would be re-rendered. You can force a rerender by passing `forceShow: true` with the region show options.
`MyApp.mainRegion.show(myView, {forceShow: true});`

- Regions now fire a new triggerMethod, `before:destroy`, triggerMethod prior to destruction of a region.

#### Views

- Returning false from `onBeforeClose` no longer prevents the view from closing.
- You can no longer return false from onBeforeClose to prevent a view
    from closing. This behavior was inconsistent with the rest of the
    library, and would require far too much logic to respect in all cases.
    Instead of returning false, you should handle your logic *before*
    calling close on the view.

- rename `close` to `destroy` for views. Close was misleading for users as to the fact that you could reuse the view if you wanted*. Destroy now clarifies the fact (in terminology and implementation)  that once a view is destroyed you can not reuse it.

- Removes duplicate and inconsistent `itemView` events. No functionality was lost with this change; use the unprefixed version instead. For instance, use `before:render` instead of `item:before:render`.
  - item:before:render
  - item:rendered
  - itemview:item:before:render
  - itemview:item:rendered
  - itemview:item:before:close
  - itemview:item:closed
- item:before:destroy
  - item:destroyed

- A new triggerMethod was added to collectionView: `before:child:remove`. 

- childEvents callbacks no longer receives the event name as the first argument.

- `itemView` within a `collectionView` is now known as `childView`. This removes confusion for new users as to the fact that you can show any type of view in your `collectionView`. All CollectionView methods that referenced `itemView` now use the same `childView` as well. For instance, `getItemView` is now `getChildView`.

- `compositeView` now calls `_onCollectionAdd` when adding a child view as compared to `addChildView` to maintain consistency with the collectionView implementation. 

- Collection and Composite Views now respect the collection comparator when rendering and when new views are added.

- collectionView’s and compositeView’s method `onChildRemove` is now known as `_onCollectionRemove`

- `collectionView` and `compositeView` now have an optional emptyViewOptions property which allows you to customize your `emptyView`.

- `renderModel` for `compositeView` is now called `_renderRoot`.

- `Layout` is now called `LayoutView`.

- Layouts now facilitate overriding the default RegionManager with a custom Class through the use of the `getRegionManager` method.

- LayoutViews now lets you specify the `regions` hash as an option upon instantiation. Previously you need to create a brand new LayoutView class to set the regions.

================

##### Removed the `Marionette.$` proxy.

The `Marionette.$` proxy of `Backbone.$` was in its own category of Marionette objects called
["Configuration."](https://github.com/marionettejs/backbone.marionette/blob/master/docs/marionette.configuration.md) It was
billed as a way to globally change the behavior of the framework, and was used everywhere internally instead of `Backbone.$`.
We couldn't find a use case for why you would want to overwrite Marionette's $ and not Backbone's, so we scrapped it.

You might be using Marionette.$ in your apps. If so, it should be an easy swap to start using Backbone.$ instead.

##### triggerMethod now calls `on`MethodName before triggering the event. Previously it was the other way around.

This is a much bigger change than you might initially think. TriggerMethod is the glue that powers Marionette. I might even
go so far as to say that if there's anything that might cause major architectural rewrites than it would be this.

TriggerMethod does two things, but in v2 the order of those things is swapped. In v1 it first triggered an event of the same name
that you passed in. For instance, `this.triggerMethod('some:event');` would call Backbone.Events' `this.trigger('some:event')`
internally. After that, it converts the name of the event to a camelcase function name, and executes it if it exists. In the above
example, it would search for `onSomeEvent` and fire it. Every Marionette event and callback are actually powered by triggerMethod
internally.

So why the change?

We believe that events on a class are more likely to be handled internally by the class first, before being responded to by
the outside world. And when you call `trigger` before firing the callback, other objects listening in will learn about
the event first. By switching the order we allow for the object to hear the event first.

##### Stricter JSHint rules were implemented for more consistent style across the codebase.

This change probably won't affect your code, but we included it in the Changelog anyway. It's just a new set of incredibly
strict linting rules to ensure that our code remains as consistent as possible.

##### A new property, `Marionette.VERSION`, was added.

This is another non-breaking change. The current version of the library is now available as `Marionette.VERSION`.

##### All instances of the word `type` in the API have been replaced with the word `class`

We think that developers are most likely to think of Marionette and Backbone objects as 'Classes' rather than 'Types'. So wherever we
had the word type in a method or option, we switched it up. We felt that this would make the API marginally easier to comprehend for
newcomers to the framework, while only being a painless regex update for folks updating the library.

##### Most classes now have `getOption` attached to their instance

Marionette.getOption is a helper method that's been around for quite some time, but in the past our Classes have called it by passing
`this` in as the first argument. For instance, `Marionette.getOption(this, 'myOption');`. We didn't like this, and wanted to make it a
class-level method. This would let us call it via `this.getOption('myOption');`. So we did.

We decided to implement this in a backwards-compatible way by introducing a new helper, `Marionette.proxyGetOption`, which wraps the
old function and binds the context. Because of this, you can continue to use the old method. Do note that the old syntax is likely to become
deprecated, so we recommend switching over as soon as possible!

##### Most classes now have `bindEntityEvents` attached to their instance

See the above.

##### Most classes now have `unbindEntityEvents` attached to their instance

See the above.

##### The built version of Marionette comes in a UMD wrapper. 

