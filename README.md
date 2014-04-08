virtualjoystick.js
==================

It is small library to emulate a virtual joystick for touchscreen.
For details, see ["Let’s Make a 3D Game: Virtual Joystick"](http://learningthreejs.com/blog/2011/12/26/let-s-make-a-3d-game-virtual-joystick/)
post on 
["learningthreejs blog"](http://learningthreejs.com).

Show Don't Tell
===============
* [examples/basic.html](http://erichlof.github.io/virtualjoystick.js/examples/basic.html)
\[[view source](https://github.com/erichlof/virtualjoystick.js/blob/master/examples/basic.html)\] :
It shows a basic usage of the library.
* [examples/dual.html](http://erichlof.github.io/virtualjoystick.js/examples/dual.html)
\[[view source](https://github.com/erichlof/virtualjoystick.js/blob/master/examples/dual.html)\] :
It shows how to have multiple virtual joystick on the same page
* [examples/stationarybase.html](http://erichlof.github.io/virtualjoystick.js/examples/stationarybase.html)
\[[view source](https://github.com/erichlof/virtualjoystick.js/blob/master/examples/stationarybase.html)\] :
It shows how to have a stationary base. by [@erichlof](https://github.com/erichlof)
* [examples/LimitStickTravelDemo.html](http://erichlof.github.io/virtualjoystick.js/examples/LimitStickTravelDemo.html)
\[[view source](https://github.com/erichlof/virtualjoystick.js/blob/master/examples/LimitStickTravelDemo.html)\] :
It shows how to limit the distance that the stick can travel from its base. by [@erichlof](https://github.com/erichlof)
* [examples/LimitStickTravelDemoStationaryBase.html](http://erichlof.github.io/virtualjoystick.js/examples/LimitStickTravelDemoStationaryBase.html)
\[[view source](https://github.com/erichlof/virtualjoystick.js/blob/master/examples/LimitStickTravelDemoStationaryBase.html)\] :
Limited Stick (same as above), but with Stationary Base. by [@erichlof](https://github.com/erichlof)
* [examples/JoystickButtonsDemo.html](http://erichlof.github.io/virtualjoystick.js/examples/JoystickButtonsDemo.html)
\[[view source](https://github.com/erichlof/virtualjoystick.js/blob/master/examples/JoystickButtonsDemo.html)\] :
Shows how to add Buttons to the Joystick. by [@erichlof](https://github.com/erichlof)

How To Install It
=================

You can install it manually. Just do 

```html
<script src='virtualjoystick.js'></script>
```

You can install with [bower](http://bower.io/).

```bash
bower install virtualjoystick.js
```

then you add that in your html

```html
<script src="bower_components/virtualjoystick.js/virtualjoystick.js"></script>
```


How To Use It ?
===============

* the Joystick and optional fire Button are very customizable
* ```opts.container``` is the
[dom element](https://developer.mozilla.org/en/DOM/element)
on which we display joystick
* ```opts.stickElement``` is the
[dom element](https://developer.mozilla.org/en/DOM/element)
which is display for the *stick* of the joystick.
* ```opts.baseElement``` is the 
[dom element](https://developer.mozilla.org/en/DOM/element)
which is display for its *base*.
* Both elements are optional with sensible default
* you may set ```opts.mouseSupport``` to true during debug.
* you may set ```opts.stationaryBase``` to true for a permanent Stationary joystick base.
* if you do use a stationary base, you must also set ```opts.baseX``` to the desired X-coordinate on the webpage and ```opts.baseY``` to the desired Y-coordinate.  The joystick base will now be fixed at this location.
* you may set ```opts.limitStickTravel``` to true in order to limit the distance that the stick can travel from its base.  This will create an invisible circle barrier that the stick cannot leave. 
* if you do use ```opts.limitStickTravel``` , you can also set ```opts.stickRadius``` to the desired radius (in pixels).  The stick will now be confined to stickRadius.  If you do not set ```opts.stickRadius``` , it will default to 100 pixels radius.

How to Use Buttons
------------------
* first, set ```opts.add1Button``` to true
* if you have a Stationary-Base Joystick, then by default, the Joystick will appear on the left and the Buttons will appear on the right.
* by default, the offset Width between Joystick and Buttons is 400 px.  This can be changed by setting ```opts.button1Offset``` to the desired integer, for example, 600.
* By default the Buttons will always be placed at the same Height on the page as the Joystick Base.
* You may manually change the Buttons' location by setting ```opts.button1X``` and ```opts.button1Y``` to the desired page X and Y coordinates.
* The first Button has a simple boolean flag attached to it called ```.button1Pressed``` which is true if pressed, false if not pressed.  If your VirtualJoystick object is called 'joystick', then this would become ```joystick.button1Pressed```
* Inside your game loop, test if ```joystick.button1Pressed``` is true, and perform the appropriate action in your code, such as 'Fire bullet'.  
