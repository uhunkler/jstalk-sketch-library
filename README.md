# jstalk-sketch-library

### About
A collection of JSTalk methods for Bohemian Coding’s Sketch. The methods support Sketch scripting - writing plugins or code that interacts with Sketch.

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
This library offers methods used in functional programming similar to the [underscore](https://github.com/jashkenas/underscore) or [Lo-Dash](http://lodash.com) libraries. The methods in the functional.jstalk are optimized for the use with JSTalk.

### jFacade.jstalk
This library offers an interface to work with Sketch in a way similar to jQuery. It adds functionality like introspection and convenience methods like “position” and “size”.

```
// Get the layer description with the layer properties 
// and log the output.
// Get properties - no parameters
var layerProperties = $(selection[0]).toString();
log(layerProperties);
```

```
// Get the selected layer and set the position and the fill color (set the first fill).
// Set properties - add the parameter/s
// Setters can be chained
var $layer = $(selection[0]);
$layer
  .position({x: 100, y: 100})
	.fills(0)
	.color("hex", "#ccc");
```

## Some Sketch jFacade examples
`examples_jFacade.jstalk``script_template_jFacade.jstalk`

### examples_jFacade.jstalk
A script with some examples how to work with jFacade and Sketch layers.

* inspectLayer
* jFacadeProperties
* swapPosition
* copiesWithVaryingOpacity

### script_template_jFacade.jstalk
A Sketch JSTalk script template with

* the library includes
* an anonymous, self executing “main” function to wrap the code
* the cleanup function call at the end

