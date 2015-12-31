![Project logo](screenshots/bin_packing_logo.png?raw=true "Bin Packing Algorithms Logo")

2D rectangular bin packing algorithms for the Haxe [bin-packing haxelib](http://lib.haxe.org/p/bin-packing). Try it out now [in your browser](http://www.samcodes.co.uk/project/rectangle-bin-packing-demo/).
	
Based on the public domain C++ bin packing implementations by [Jukka Jylänki](https://github.com/juj/RectangleBinPack).

## Features ##
* Several fast approximate bin packing algorithms.
* "Occupancy rate" measure to compare packing performance.
* Configurable packing heuristics.

## Usage ##

Try the [demo](http://www.samcodes.co.uk/project/rectangle-bin-packing-demo/) in your browser and refer to the [example code](https://github.com/Tw1ddle/Rectangle-Bin-Packing-Demo/).

Basic usage example:

```haxe
var binWidth:Int = 800;
var binHeight:Int = 400;
var useWasteMap:Bool = true;
var packer = new SkylinePack(binWidth, binHeight, useWasteMap);

var rectWidth:Int = 20;
var rectHeight:Int = 40;
var heuristic:LevelChoiceHeuristic = LevelChoiceHeuristic.MinWasteFit;
var rect:Rect = skylinePack.insert(rectWidth, rectHeight, heuristic);

if(rect == null) {
	trace("Failed to pack rect");
} else {
	trace("Inserted rect at: " + Std.string(rect.x) + "," + Std.string(rect.y));
}
```

## Install ##

Get the Haxe library code here or through haxelib.

Include it in your ```.hxml```
```
-lib bin-packing
```

Or add it to your ```Project.xml```:
```
<haxelib name="bin-packing" />
```

## Screenshots ##
Screenshots of the [demo](https://github.com/Tw1ddle/Rectangle-Bin-Packing-Demo/):

![Screenshot](screenshots/screenshot1.png?raw=true "Bin Packing Algorithms screenshot 1")

![Screenshot](screenshots/screenshot2.png?raw=true "Bin Packing Algorithms screenshot 2")

## Notes ##
* Most of the algorithms are ported from public domain C++ implementations by [Jukka Jylänki](https://github.com/juj/RectangleBinPack).
* For details about the algorithms, see Jukka's [blog posts](http://clb.demon.fi/projects/even-more-rectangle-bin-packing) and [paper](http://clb.demon.fi/files/RectangleBinPack.pdf).
* The haxelib supports every Haxe target, but has not been thoroughly tested or optimized for performance, especially on native targets.
* If you have any questions or suggestions then [get in touch](http://samcodes.co.uk/contact).