# Angular - core directives

## Objectives
 1. understand the value of ng-repeat
 2. use ng-if, ng-switch and ng-class
 3. find the various event directives available such as ng-focus
 4. use event directives to call methods in a controller

## Templating in angular js

`{{value}}` is a basic way to display a value in the view. To have a complete
templating engine we still need following things:
 * loops that allow to iterate over collection & display each of its elements
 * control mechanism - ifs, switches - to conditionally change the view
 * bind events form the view

All of those features are provided by angular core
[directives](https://docs.angularjs.org/guide/directive) - elements & attributes
which change default behavior of elements.

### Loops

Loops are created by the `ng-repeat` directive. It is used as an attribute at any
element; and it's repeat the element & it's content for each value in a provided
collection. The following code:

```html
<ul>
  <li ng-repeat="element in list">
    {{element}}
  </li>
</ul>
```

will display each element form the list as one bullet point of the list.

Read more in a
[documentation](https://docs.angularjs.org/api/ng/directive/ngRepeat).

#### Note!

If you are using `ng-repeat` with `ng-model` please read
[this discussion](http://stackoverflow.com/a/13715352).

### Conditional directives

To change templates we have following directives available:
* [ng-switch](https://docs.angularjs.org/api/ng/directive/ngSwitch):
```html
<div ng-switch="expression">
  <span ng-switch-when="matchValue1">...</span>
  <span ng-switch-when="matchValue2">...</span>
  <span ng-switch-default>...</span>
</div>
```
* [ng-if](https://docs.angularjs.org/api/ng/directive/ngIf):
```html
<div ng-if="expression">
</div>
```

Both directives remove or add elements depending on the value of expression.

### Binding to events

In all previews examples we were biding values insides view. To have a complete
templating engine we need a way to fire a controller's method from the view.
Angular core provides quite a few directives for that:
 * [ng-click](https://docs.angularjs.org/api/ng/directive/ngSwitch)
 * [ng-keydown](https://docs.angularjs.org/api/ng/directive/ngKeydown)
 * [ng-copy](https://docs.angularjs.org/api/ng/directive/ngCopy)

All of them are attributes, and accepts a function call as a value:

```html
<button ng-click="close()">Close</button>
```

## Attributes

Within angular view we can use `{{variables}}` inside elements, or even to
provide a value of attributes:

```html
<img src="{{source}}" />

<a href="{{link}}">

<div class="{{class}}">
```

There are multiple angular wrappers for the native attributes:
 * [ng-href](https://docs.angularjs.org/api/ng/directive/ngHref)
 * [ng-src](https://docs.angularjs.org/api/ng/directive/ngSrc)
 * [ng-class](https://docs.angularjs.org/api/ng/directive/ngClass)
 * etc.

The first two avoid confusing browser to use uncompiled value as a image source;
or link direction. The ng-class provides more flexible way of setting classes
at the element. See more in the documentation.
