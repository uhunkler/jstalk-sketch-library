# jstalk-sketch-library

### About
A collection of JSTalk methods for Bohemian Coding’s Sketch. The methods support Sketch scripting - writing plugins or code that interacts with Sketch.

The library is work in progress.

To use the libraries and the examples please copy the library folder and the two example “.jstalk” files into the Sketch “Plugins” folder.

## Libraries
`library/sketch_connector.jstalk`  
`library/functional.jstalk`  
`library/jFacade.jstalk`  

### sketch_connector.jstalk
This library offers methods for common tasks
* Create an universal connector to Sketch to allow to run JSTalk scripts as Sketch plugins (called from the Sketch “Plugin” menu) **and** from JSTalkEditor, the command line or from a JSTalk enabled editor via the `jstalk` command without changes.
* Offer some frequently used methods.
* Offer methods to workaround known Sketch issues.

### functional.jstalk
This library offers methods used in functional programming similar to the [underscore](https://github.com/jashkenas/underscore) or [Lo-Dash](http://lodash.com) libraries. The methods in functional.jstalk are optimized for the use with JSTalk.

### jFacade.jstalk
This library offers an interface to work with Sketch in a way similar to jQuery. It adds functionality like introspection and convenience methods like “position” and “size”.

```
// Get the layer description with the layer properties 
// and log the output.
var layerProperties = $(selection[0]).toString();
log(layerProperties);
```

```
// Get the selected layer and set the position and the fill color (set the first fill).
// Get properties - no parameters
// Set properties - add parameter/s
// Setters can be chained
var $layer = $(selection[0]),
  pos = $layer.position();

// jlog prints a JSON stringified JavaScript/jFacade object
jlog(pos); // {x:val, y:val}

$layer
  .position({x: 100, y: 100})
  .fills(0)
  .color("hex", "#ccc");
```

## Some Sketch jFacade examples
`examples_jFacade.jstalk`  
`script_template_jFacade.jstalk`  

### examples_jFacade.jstalk
A script with some examples how to work with jFacade and Sketch layers.

* inspectLayer
* jFacadeProperties
* swapPosition
* copiesWithVaryingOpacity

### script_template_jFacade.jstalk
A Sketch JSTalk script template.

```
#import 'library/sketch_connector.jstalk'
#import 'library/functional.jstalk'
#import 'library/jFacade.jstalk'

// Anonymous function holds the code.
// Helps to avoid Sketch memory issue based crashes.
// Is executed automatically.
(function main() {
  // Check if an element is selected
  if (sketch.checkSelection(1, "Please select an element.")) {
    // your code ...
  }
}());

// Set all defined objects to null to force garbage collection,
// otherwise Sketch may crash.
sketch.cleanup();
```

## ToDos
* Write usage documentation with code examples
* Write the jFacade documentation - how it works, how to extend the functionality
* Add more comments in the library code
* Add more methods to the functional library
* Add more methods to the jFacade library for better Sketch coverage


