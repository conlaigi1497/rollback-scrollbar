# rollback-scrollbar

A custom scrollbar written in pure AngularJS.

Works with the mouse and on touch screen.

Tired of using jquery for a stupid scrollbar? well, this directive is just for you.

## Usage

1. Add rollback-scrollbar.min.js to you main file (index.html)

you can download this by:

- using bower and running `bower install rollback-scrollbar`
- Download the [production version][min] or the [development version][max].

[min]: https://raw.github.com/conlaigi1497/rollback-scrollbar/master/dist/angular-rollback-scrollbar.min.js
[max]: https://raw.github.com/conlaigi1497/rollback-scrollbar/master/dist/angular-rollback-scrollbar.js

In your web page:

```html
<script src="angular.js"></script>
<script src="dist/rollback-scrollbar.min.js"></script>
<link rel="stylesheet" href="dist/rollback-scrollbar.min.css" />
```

2. Set `ngScrollbar` as a dependency in your module

```javascript
var myapp = angular.module("myapp", ["ngScrollbar"]);
```

3. Add rollback-scrollbar directive to the wanted element, example:

```html
<div class="scrollme" rollback-scrollbar>....</div>
```

## Rebuild the scrollbar

In case you need to rebuild the scrollbar, you may tell rollback-scrollbar to rebuild it for you by broadcasting an event.
It's useful to use this option when the size or visibility of the container is dynamic and during the link phase the size can't be determined.

```html
<div class="scrollme" rollback-scrollbar rebuild-on="rebuild:me">....</div>
```

```javascript
// rebuild the scrollbar
$scope.$broadcast("rebuild:me");
```

In case you need to rebuild the scrollbar on every window's resize, you may use "rebuild-on-resize" option.

```html
<div class="scrollme" rollback-scrollbar rebuild-on-resize>....</div>
```

In case you need to stick content to bottom (chat or something) use "bottom" option.

```html
<div class="scrollme" rollback-scrollbar bottom>....</div>
```

## Events and Flags

On rebuilding the scrollbar you can get notified by 2 events

```javascript
$scope.$on("scrollbar.show", function () {
  console.log("Scrollbar show");
});
$scope.$on("scrollbar.hide", function () {
  console.log("Scrollbar hide");
});
```

Or you can use "is-bar-shown" option. It should be read-only

```html
<div class="scrollme" rollback-scrollbar is-bar-shown="flag">....</div>
<div>Bar shown: {{flag}}</div>
```

## Examples

See the example in the respository.
[example/index.html](https://htmlpreview.github.io/?https://github.com/conlaigi1497/rollback-scrollbar/blob/master/example/index.html)

[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/conlaigi1497/rollback-scrollbar/trend.png)](https://bitdeli.com/free "Bitdeli Badge")
