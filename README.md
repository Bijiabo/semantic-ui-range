# semantic-ui-range
Add-on range slider for Semantic UI

[Demo](http://codepen.io/tyleryasaka/pen/KVqPbo)

I created the range slider for Semantic UI when I found that one currently did not exist.

The range slider is responsive and works for both mouse and touchscreen on all the devices it has been tested on. It uses standard css/javascript (no hacks) so it should render well on just about any remotely modern device. That said I have not thoroughly tested it, so let me know if you encounter any bugs.

##Usage

###Step 1

Add the range.js and range.css files from this repo to your project.

###Step 2

Add the range slider html.

	<div class="ui range" id="my-range"></div>

###Step 3

Instantiate the range slider with jQuery:

	$(document).ready(function() {
		$('#my-range').range({
			min: 0,
			max: 10,
			start: 5
		});
	});

## Configuration Options

Notice the settings object you pass into the jQuery function in step 3. There are 6 settings you can pass in:
* min (number; required) - the lowest value (inclusive) of the range
* max (number; required) - the highest value (inclusive) of the range
* start (number; optional) - the initial value of the range (must be between min and max)
* step (number; optional) - the increment amount between values (defaults to 1)
* input (string; optional) - A jQuery identifier string (such as '#my-input') to specify an html input to receive the new range value each time it is changed
* onChange (function; optional) - function to call each time the value of the range changes; a single parameter with the new value is passed to this function

## *Getting* the slider value programmatically

Use the `onChange` callback in the configuration options. For example:

    var myRangeValue; // your javascript variable that will store the value of the slider

    $('#range').range({
      min: 0,
      max: 100,
      start: 5,
      onChange: function(val) { myRangeValue = val; } // assigning the callback argument to your variable each time the value changes
    });

## *Setting* the slider value programmatically

You may also set the slider value with jQuery using the 'setValue' query like so:

    $('#range').range('setValue', 17); // Sets slider with id 'range' to value 17

Note that this will only work on a slider that has already been instantiated.

## Demo

Check out the [demo](http://codepen.io/tyleryasaka/pen/KVqPbo) for examples.
