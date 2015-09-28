# CountUp.js
CountUp.js is a dependency-free, lightweight JavaScript "class" that can be used to quickly create animations that display numerical data in a more interesting way.

Despite its name, CountUp can count in either direction, depending on the `startVal` and `endVal` params that you pass.

CountUp.js supports all browsers.

##[Try the demo](http://inorganik.github.io/countUp.js)

## Installation

The only file you need is countUp.js. 

If you want to get fancy with build systems, a gulpfile is included. [Read more here](contributing.md).

## Angular directive
Included is an angular module. Use the count-up attribute to quickly create an animation. It also integrates nicely with the angular-scroll-spy directive. **[Check out the angular demo](http://inorganik.github.io/angular-scroll-spy).**

## Usage:
Params:
- `target` = id of html element, input, svg text element, or var of previously selected element/input where counting occurs
- `startVal` = the value you want to begin at
- `endVal` = the value you want to arrive at
- `decimals` = (optional) number of decimal places in number, default 0 
- `duration` = (optional) duration in seconds, default 2 
- `options` = (see demo, optional) formatting/easing options object 

Decimals, duration, and options can be left out to use the default values.

```js
var numAnim = new CountUp("SomeElementYouWantToAnimate", 24.02, 99.99);
numAnim.start();
```

with optional callback:

```js
numAnim.start(someMethodToCallOnComplete);

// or an anonymous function
numAnim.start(function() {
    // do something
})
```
For angular:
```html
<h2 count-up id="numberAnimation" end-val="873.4" decimals="1" duration="3"></h2>
```
Width angular-scroll-spy:
```html
<h2 count-up id="numberAnimation" end-val="873.4" decimals="1" duration="3" scroll-spy-event="elementFirstScrolledIntoView" scroll-spy></h2>
```

## Other methods:
Toggle pause/resume:

```js
numAnim.pauseResume();
```

Reset an animation:

```js
numAnim.reset();
```

Update the end value and animate:

```js
var someValue = 1337;
numAnim.update(someValue);
```

## License & Contributing
- Details on the license [can be found here](LICENSE.md)
- Details on running tests and contributing [can be found here](contributing.md)
