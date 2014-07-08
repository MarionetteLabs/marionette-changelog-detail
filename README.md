# Marionette Changelog Detail

The v2 CHANGELOG is meant to be a succinct description of each change made for v2. But
such terse statements are only so helpful. You might often be left wondering why a particular
change was made. That's question the Changelog Detail is intended to answer.

To begin, select a v2 change from the menu below.

### v2 Changelog

#### [General](https://github.com/Puppets/marionette-changelog-detail/blob/master/README.md#general-1)

- [Removed the `Marionette.$` proxy. We are now using `Backbone.$` instead.](https://github.com/Puppets/marionette-changelog-detail#removed-the-marionette-proxy)

- [triggerMethod now calls `on`MethodName before triggering the event. Previously it was the other way around.](https://github.com/Puppets/marionette-changelog-detail#triggermethod-now-calls-onmethodname-before-triggering-the-event-previously-it-was-the-other-way-around)

- [Stricter JSHint rules were implemented for more consistent style across the codebase.](https://github.com/Puppets/marionette-changelog-detail#stricter-jshint-rules-were-implemented-for-more-consistent-style-across-the-codebase)

- [A new property, `Marionette.VERSION`, was added.](https://github.com/Puppets/marionette-changelog-detail#a-new-property-marionetteversion-was-added)

- [All instances of the word `type` in the API have been replaced with the word `class`](https://github.com/Puppets/marionette-changelog-detail#all-instances-of-the-word-type-in-the-api-have-been-replaced-with-the-word-class)

- [Most classes now have `getOption` attached to their instance](https://github.com/Puppets/marionette-changelog-detail#most-classes-now-have-getoption-attached-to-their-instance)

- [Most classes now have `bindEntityEvents` attached to their instance](https://github.com/Puppets/marionette-changelog-detail#most-classes-now-have-bindentityevents-attached-to-their-instance)

- [Most classes now have `unbindEntityEvents` attached to their instance](https://github.com/Puppets/marionette-changelog-detail#most-classes-now-have-unbindentityevents-attached-to-their-instance)

- [The built version of Marionette comes in a UMD wrapper.](https://github.com/Puppets/marionette-changelog-detail#the-built-version-of-marionette-comes-in-a-umd-wrapper)

#### [Applications and Modules](https://github.com/Puppets/marionette-changelog-detail#applications-and-modules-1)

- [The arguments of a Module’s initialize function are now consistent with Module constructor argument order.](https://github.com/Puppets/marionette-changelog-detail#the-arguments-of-a-modules-initialize-function-are-now-consistent-with-module-constructor-argument-order)

- [Application’s `initialize` triggerMethods have been renamed](https://github.com/Puppets/marionette-changelog-detail#applications-initialize-triggermethods-have-been-renamed)

- [The Application message system is now the global Channel](https://github.com/Puppets/marionette-changelog-detail#the-application-message-system-is-now-the-global-channel)

- [Applications have two new triggerMethods: `before:region:add` and `before:region:remove`](https://github.com/Puppets/marionette-changelog-detail#applications-have-two-new-triggermethods-beforeregionadd-and-beforeregionremove)

#### [Controllers](https://github.com/Puppets/marionette-changelog-detail#controllers-1)

- [`stopListening` is now called after the `destroy` triggerMethod is called.](https://github.com/Puppets/marionette-changelog-detail#stoplistening-is-now-called-after-the-destroy-triggermethod-is-called)

#### [Behaviors](https://github.com/Puppets/marionette-changelog-detail#behaviors-1)

- [`Behaviors` now support a means to group behaviors together.](https://github.com/Puppets/marionette-changelog-detail#behaviors-now-support-a-means-to-group-behaviors-together)

#### [Regions](https://github.com/Puppets/marionette-changelog-detail#regions-1)

- [Regions now throw an error when they are instantiated with a nonexistent el.](https://github.com/Puppets/marionette-changelog-detail#regions-now-throw-an-error-when-they-are-instantiated-with-a-nonexistent-el)

- [Regions now use `.innerHtml` when clearing contents as compared this `this.$el.empty()`.](https://github.com/Puppets/marionette-changelog-detail#regions-now-use-innerhtml-when-clearing-contents-as-compared-this-thiselempty)

- [`region.show` now return `this`, just like how a view’s render returns `this`.](https://github.com/Puppets/marionette-changelog-detail#regionshow-now-return-this-just-like-how-a-views-render-returns-this)

- [Regions trigger two new events, `before:swap` and `swap`, when it swaps views when calling `show`.](https://github.com/Puppets/marionette-changelog-detail#regions-trigger-two-new-events-beforeswap-and-swap-when-it-swaps-views-when-calling-show)

- [Region’s el can now be a DOM node / DOM string selector / Jquery selector instance, just like a View’s el.](https://github.com/Puppets/marionette-changelog-detail#regions-el-can-now-be-a-dom-node--dom-string-selector--jquery-selector-instance-just-like-a-views-el)

- [Region’s ensureEl is now _ensureElement](https://github.com/Puppets/marionette-changelog-detail#regions-ensureel-is-now--ensureelement)

- [Regions now expose region.el and region.$el, just like View’s.](https://github.com/Puppets/marionette-changelog-detail#regions-now-expose-regionel-and-regionel-just-like-views)

- [Calling show on a region with the same view that is currently shown is now a noop.](https://github.com/Puppets/marionette-changelog-detail#calling-show-on-a-region-with-the-same-view-that-is-currently-shown-is-now-a-noop)

- [Regions now fire a new triggerMethod, `before:destroy`, triggerMethod prior to destruction of a region.](https://github.com/Puppets/marionette-changelog-detail#regions-now-fire-a-new-triggermethod-beforedestroy-triggermethod)

#### [Views](https://github.com/Puppets/marionette-changelog-detail#views-1)

- [Returning false from `onBeforeClose` no longer prevents the view from closing.](https://github.com/Puppets/marionette-changelog-detail#returning-false-from-onbeforeclose-no-longer-prevents-the-view-from-closing)

- [rename `close` to `destroy` for views.](https://github.com/Puppets/marionette-changelog-detail#rename-close-to-destroy-for-views)

- [Removes duplicate and inconsistent `itemView` events.](https://github.com/Puppets/marionette-changelog-detail#removes-duplicate-and-inconsistent-itemview-events)

- [A new triggerMethod was added to collectionView: `before:child:remove`.](https://github.com/Puppets/marionette-changelog-detail#a-new-triggermethod-was-added-to-collectionview-beforechildremove) 

- [childEvents callbacks no longer receives the event name as the first argument.](https://github.com/Puppets/marionette-changelog-detail#childevents-callbacks-no-longer-receives-the-event-name-as-the-first-argument)

- [`itemView` within a `collectionView` is now known as `childView`.](https://github.com/Puppets/marionette-changelog-detail#itemview-within-a-collectionview-is-now-known-as-childview)

- [`compositeView` now calls `_onCollectionAdd` when adding a child view as compared to `addChildView`](https://github.com/Puppets/marionette-changelog-detail#compositeview-now-calls-_oncollectionadd-when-adding-a-child-model-as-compared-to-addchildview)

- [Collection and Composite Views now respect the collection comparator when rendering and when new views are added.](https://github.com/Puppets/marionette-changelog-detail#collectionviews-and-compositeviews-method-onchildremove-is-now-known-as-_oncollectionremove)

- [collectionView’s and compositeView’s method `onChildRemove` is now known as `_onCollectionRemove`](https://github.com/Puppets/marionette-changelog-detail#collection-and-composite-views-now-respect-the-collection-comparator-when-rendering-and-when-new-views-are-added)

- [`collectionView` and `compositeView` now have an optional emptyViewOptions property which allows you to customize your `emptyView`.](https://github.com/Puppets/marionette-changelog-detail#collectionview-and-compositeview-now-have-an-optional-emptyviewoptions-property-which-allows-you-to-customize-your-emptyview)

- [`renderModel` for `compositeView` is now called `_renderRoot`.](https://github.com/Puppets/marionette-changelog-detail#rendermodel-for-compositeview-is-now-called-_renderroot)

- [`Layout` is now called `LayoutView`.](https://github.com/Puppets/marionette-changelog-detail#layout-is-now-called-layoutview)

- [Layouts now facilitate overriding the default RegionManager with a custom Class through the use of the `getRegionManager` method.](https://github.com/Puppets/marionette-changelog-detail#layouts-now-facilitate-overriding-the-default-regionmanager-with-a-custom-class-through-the-use-of-the-getregionmanager-method)

- [LayoutViews now lets you specify the `regions` hash as an option upon instantiation.](https://github.com/Puppets/marionette-changelog-detail#layoutviews-now-lets-you-specify-the-regions-hash-as-an-option-upon-instantiation)

================

#### General

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

There used to be three builds of Marionette: just the core files (no Wreqr or Babysitter), a bundled version of the core,
and a a UMD build of the core. There are just two builds now: bundled and not-bundled. Both are UMD.

The biggest change here is that the directory structure of the built files has changed. Be sure to update your build
process to reference the new files, especially if you use UMD Marionette!

#### Applications and Modules

##### The arguments of a Module’s initialize function are now consistent with Module constructor argument order. 

When we added the initialize function to Modules we inexplicably left out the second argument from the function. Our mistake. We
quickly added it back, but had to add it as the *third* argument to retain backwards compatible. This created a mis-match between
initialize and constructor that we resolved to fix as soon as possible. So we did, in v2.

##### Application’s `initialize` triggerMethods have been renamed

This one might be a bit confusing to describe, but I'll do my best. Let's start at the beginning. In the Backbone world, as you might
already know, objects have an initialize function that is called when you instantiate a new instance of that object. Because of this,
we like to think of the verb `initialize` being reserved from when things are started up. But Applications didn't use it like that.

Instead, Applications were using `initialize` to refer to when they were being **started**! This was bad for a few reasons. Firstly, it
made no sense given the above. It also made no sense because modules had `before:start` and `start` triggerMethods. To make matters stranger,
the Application still had a `start` callback that was identical to the `initialize` callback other than the name.

We know, we know. Super confusing. But there is a bit of logic to this madness. You see, Applications have a method `addInitializers`, which
adds a series of methods to be called when the Application begins. We think this is the origin of using the verb in this context came from. We
also dislike the name of that method, but that might be changed in a future version of Marionette.

##### The Application message system is now the global Channel

Applications have an instance of an EventAggregator, Commands, and RequestResponse on them. A common use case for these is as a global
messaging channel for the entire application. A recent update to Wreqr added an actual Channel object, which is just a collection of the
three messaging systems with an associated name. It only made sense for us to replace the unnamed Application instances with a channel
named 'global.'

##### Applications have two new triggerMethods: `before:region:add` and `before:region:remove`

You might be familiar with the fact that you can attach Regions directly to your application. What you might not know is that this is
powered by an often-forgotten Marionette class called RegionManager. The details don't really matter, but what does matter is that the
RegionManager has triggerMethods that are called before regions are added and removed. For whatever reason these weren't being forwarded
onto the Application. Now they are!

#### Controllers

##### `stopListening` is now called after the `destroy` triggerMethod is called.

This is a subtle change, like many of the evented changes seem to be. `stopListening` removes all of the event listeners from the Controller,
but right now is called before the `destroy` triggerMethod. In Views, the other classes that call stopListening in their destroy function,
the stopListening happens after close. So we changed it for consistency in the library.

#### Behaviors

##### `Behaviors` now support a means to group behaviors together.

Sometimes you might want to group your behaviors together. For instance, maybe you have form validation, modal, and keybinding behaviors that
are meant to work together in some view that was designed to represent a Form. Instead of referencing all three behaviors in each FormView,
you can now pull in a single Behavior that is a collection of the three.

#### Regions

##### Regions now throw an error when they are instantiated with a nonexistent el.

Regions only work when you've got an el to work with. Previously you could instantiate a view without an el and nothing would happen,
which was very difficult to debug in big applications. This change causes an error to be thrown when the view's el can't be found,
which should help with the debugging process.

If you're one of the rare cases where you might want a region to exist before its el does, you can simply create a new class and overwrite
the constructor.

##### Regions now use `.innerHtml` when clearing contents as compared this `this.$el.empty()`.

This change provides us with a huge performance boost, with no loss of functionality. But it does place more responsibility on you as a
developer. Whereas regions would previously clean up any event listeners, preventing memory leaks, they no longer do. This is because it
isn't the responsibility of the region to clean up event listeners. Regions themselves don't have any event listeners out of the box
in Marionette, so they weren't ever cleaning up their own events. Instead, they were handling a responsibility that belongs to the View.

Just keep in mind that if you're using jQuery plugins or setting custom DOM listeners for your views, be sure to shut them down in the
`onBeforeDestroy` callback!

##### `region.show` now return `this`, just like how a view’s render returns `this`

One of the things we did in v2 was make the API of regions more like views. We like this because both Classes are related to displaying content.
The only specification Backbone gives to View's render is that it should return `this`, so we added that same feature to a Region's `show`
method, which is analogous to View's render method.

##### Regions trigger two new events, `before:swap` and `swap`, when it swaps views when calling `show`.

You're probably used to the `show` triggerMethods of Regions, and we added new ones for you to work with. The `swap` events are only triggered
when a view that already has a view is showing a new one. In other words, `show` is called even when the view goes from being empty to filled,
whereas `swap` is only changed when it goes from being occupied by one view to being occupied by another.

##### Region’s el can now be a DOM node / DOM string selector / Jquery selector instance, just like a View’s el.

One of the great features of Views is the flexibility in specifying their `el`. But Regions never had the same flexibility, always
requiring you to pass a selector string. In v2 that has changed!

##### Region’s ensureEl is now _ensureElement

Region's `ensureEl` functioned in the exact same way that View's `_ensureElement` did. So we renamed it.

##### Regions now expose region.el and region.$el, just like View’s.

Just like Views, you can now access the Region's raw `el`. In v1 this property always remained the selector string. To access the selector
you can always use `this.$el.selector`.

##### Calling show on a region with the same view that is currently shown is now a noop.

The `show` method of a region used to be really destructive. If you went to show a view that was already in the region, that view would
be completely re-rendered. Rendering is an expensive process, so we decided to make this method idempotent in v2. All that means is you can
call it any number of times with the same view, but it will only render that view on the first try.

To get the old functionality back, pass `forceShow:true` in the options.

```js
this.region.show(myView, {forceShow: true});
```

##### Regions now fire a new triggerMethod, `before:destroy`, triggerMethod.

Every Marionette Class let you tune in before the destroy happened with `onBeforeDestroy`. But Regions were an unexplained exception to that rule.
We decided to make it consistent by adding the before destroy hook to the Region class.

#### Views

##### Returning false from `onBeforeClose` no longer prevents the view from closing.

Of all of the triggerMethod callbacks, `onBeforeClose` stood out for this unique feature. If you returned false from it, it would
actually prevent the view from closing. This might seem useful, but it wasn't consistent with the rest of the library, and, maybe
more frighteningly, it wasn't respected by Regions.

Instead of making sure we handle this situation in every case, we decided it would be better to remove it. Instead of using a before
hook to cancel an action we believe you should determine that logic before you ever fire the action.

To give an example, instead of returning false in your onBeforeClose, you should have code like this:

```js
if (myCondition) {
  this.close();
} else {
  // I am not closing!
}
```

##### rename `close` to `destroy` for views.

Frequently we are asked why a region has completely removed a view from existence when it calls close on it. These users ask, "we just
closed it, can't we open it again?" For those more familiar with the library, you might know that the answer is no, you can't just reopen it
because close is meant to be a permanent action; it's intended to set the view up for garbage collection.

Because of this we decided to pick a verb that carries this same weight, and destroy fit the bill.

##### Removes duplicate and inconsistent `itemView` events.

ItemViews had 

##### A new triggerMethod was added to collectionView: `before:child:remove`. 

Believe it not, collections never used to alert you when before child view was removed. Well, they do now.

##### childEvents callbacks no longer receives the event name as the first argument.

CollectionViews have a `childEvents` hash, which forwards child events to callbacks on the parent view itself. However,
the arguments passed to these callbacks were inconsistent with the normal callbacks for triggers. The inconsistency was due to
the first argument of the callback, which for `childEvents` was the name of the event. In other situations the callbacks for Backbone Events
don't receive the name of the event at all. This change makes `childEvents` arguments consistent with the arguments for any other callback.

##### `itemView` within a `collectionView` is now known as `childView`.

One of the more confusing bits of the Marionette API was the use of the phrase `ItemView` in the CollectionView API. This
suggests that you can only use ItemViews with CollectionViews. If you're familiar with Marionette you know that this isn't the case:
you can use any View class. We hope the more general term 'childView' will make this more explicit.

##### `compositeView` now calls `_onCollectionAdd` when adding a child model as compared to `addChildView`

We decided to change this method to be private, as the internals of a collection view interacting with its collection shouldn't be
overridden. We also decided to reference the changing collection rather than adding more API methods that reference children views,
as the collection view API is becoming quite full with similar-sounding method names.

##### collectionView’s and compositeView’s method `onChildRemove` is now known as `_onCollectionRemove`

The reasoning here is really identical to the above.

##### Collection and Composite Views now respect the collection comparator when rendering and when new views are added.

One of the most-requested features for Marionette views were automatically sorted Collections. You've now got it! If you'd
rather opt out of this functionality, just pass the new `sort` option to be false.

```js
this.collectionView = new MyCollectionView({
  sort: false
});
```

##### `collectionView` and `compositeView` now have an optional emptyViewOptions property which allows you to customize your `emptyView`.

To complement the `childViewOptions` you can use to style your child views we now have `emptyViewOptions`. It works exactly as you'd expect.

##### `renderModel` for `compositeView` is now called `_renderRoot`.

If you're not familiar with this method, it's the one that renders the template of the Composite View. We began by deciding that it
should be private, then went on to decide that calling it `renderModel` was really confusing, as many people working with Composite Views
think of the models as being in the ones in the collection. So we decided to call it the root as a reference to the visualization of
a composite view as a tree view.

##### `Layout` is now called `LayoutView`.

Layouts can be difficult for newcomers to approach, and we don't think their name helps at all. A Layout is really just a View beneath all of
its fancy features, so we decided to rename it to `LayoutView` in v2. 

##### Layouts now facilitate overriding the default RegionManager with a custom Class through the use of the `getRegionManager` method.

Ah, yes, the RegionManager. Layouts get their Region superpowers from a Marionette class called the RegionManager. It used to be difficult
to override the RegionManager because there was no helper function to do so. Now you can use `getRegionManager` to easily provide
your own, should you feel so inclined.

##### LayoutViews now lets you specify the `regions` hash as an option upon instantiation.

There was previously no way to instantiate a LayoutView by itself. You absolutely needed to create a new Class for it. The reason for this
is because the `regions` property was ignored if you passed it in as an option to Regions. In v2 we changed this, so you can now define a
basic LayoutView without creating a brand new class.

```js
var myLayout = new LayoutView({
  model: myModel,
  template: myTemplate,
  regions: {
    myDiv: 'div.mine'
  }
});
```
