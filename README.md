angular-swipe
=============

Simple vertical/horizontal swipe gesture directives and a swipe service for angular js >= 1.4. Small extension of the existing angular $swipe service.

## Fork Info

This is a Fork from marmorkuchen-net/angular-swipe. It has the following extra features/changes:

1- Vertical swiping can be enabled/disabled by passing a third paramater to the service swipe.bind(elem,{},true/false)

2- swiping now continutes if the mouse/finger goes out of the element bounds. i.e 'move' handler is called even if the pointer is out. Also 'end' handler fires upon releasing in anywhere in the window.

### Fork -> To do
1- impelemnt the above features to the directive as well not just the service.


## Install

+ Add this line to your *bower.json* dependencies and run *bower install* afterwards.

>
``` JavaScript
"angular-swipe": "~0.1.0"
```

+ Include the required source file (this path or similar)

>
``` html
<script src="bower_components/dist/angular-swipe.js"></script>
```

+ Inject the `swipe` module into your app.

>
``` JavaScript
angular.module('app', ['swipe']);
```

## Usage

#### Module Name (Dependency)

* swipe

#### Directives

* ng-swipe-up
* ng-swipe-down
* ng-swipe-left
* ng-swipe-right

#### Directive Attributes

`ng-swipe-disable-mouse` "This attribute is useful for text that should still be selectable by the mouse and not trigger the swipe action."

#### Service

* swipe

## Example

>
```html
<div class="page" ng-controller="AppCtrl">
    <div class="container" ng-swipe-up="swipe($event)">
      <h1>Swipe me up!</h1>
    </div>
</div>
```

>
```JavaScript
var app = angular.module('app', [ 'swipe' ]);
app.controller('AppCtrl', function AppCtrl($scope) {
  $scope.swipe = function($event) {
    console.log($event);
  };
})
```

## Known issues and workarounds

* ng-swipe-up and ng-swipe-down uses preventDefault when you start swiping. This prevents clicks from giving focus to input fields. Adding a `noPreventDefault` class to these elements will not preventDefault when the swipe start on them and thus allow clicks to work.
