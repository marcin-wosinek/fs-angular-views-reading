# Angular - core directives

## Objectives
 1. understand the value of ng-repeat
 2. use ngif, ngswitch and ngclass
 3. find the various event directives available such as ngfocus
 4. use event directives to call methods in a controller

## Templating in angular js

`{{value}}` is a basic way to display a value in the view. To have a complete
templating engine we still need following things:
 * loops that allow to iterate over collection & display each of the elements
 * control mechanism - ifs, switches - to conditionally change view
 * bind events form the view

All of those features are provided by angular core
[directives](https://docs.angularjs.org/guide/directive) - elements & attributes
which change default behavior of elements.

### Loops

Loops are created by `ng-repeat` directive. It is used as an attribute at any
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
[this discussion](http://stackoverflow.com/a/13715352)

### Control directives

### Binding to events

## Attributes

Within angular view we can use `{{variables}}` inside elements, or even to
provide a value of attributes:

```html
<img src="{{source}}" />

<a href="{{link}}">

<div class="{{class}}">
```

There is multiple angular wrapper for native attributes:
 * [ng-href](https://docs.angularjs.org/api/ng/directive/ngHref)
 * [ng-src](https://docs.angularjs.org/api/ng/directive/ngSrc)
 * [ng-class](https://docs.angularjs.org/api/ng/directive/ngClass)
 * etc.

The first two avoid confusing browser to use uncompiled value as a image source;
or link direction. The ng-class provides more flexible way of setting classes
at the element. See more in the documentation.
