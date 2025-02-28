
BookBlock
=========

A jQuery plugin that will create a booklet-like component that let's you navigate through its items by flipping the pages.

[article on Codrops](http://tympanus.net/codrops/2012/09/03/bookblock-a-content-flip-plugin/)

[demo](http://tympanus.net/Development/BookBlock/)

License: http://tympanus.net/codrops/licensing/


## USAGE

#### HTML side
```
<div id="bb-bookblock" class="bb-bookblock">
	<div class="bb-item">
		<!-- custom content -->
	</div>
	<div class="bb-item">
		<!-- ... -->
	</div>
	<div class="bb-item">
		<!-- ... -->
	</div>
	<div class="bb-item">
		<!-- ... -->
	</div>
	<!-- ... -->
</div>

<nav>
	<a id="bb-nav-first" href="#" class="bb-custom-icon bb-custom-icon-first"> </a>
	<a id="bb-nav-prev" href="#" class="bb-custom-icon bb-custom-icon-arrow-left"> </a>
	<a id="bb-nav-next" href="#" class="bb-custom-icon bb-custom-icon-arrow-right"> </a>
	<a id="bb-nav-last" href="#" class="bb-custom-icon bb-custom-icon-last"> </a>
</nav>
```

#### BookBlock Configuration Options

```js
// page to start on
startPage : 1,
// vertical or horizontal flip
orientation : 'vertical',
// ltr (left to right) or rtl (right to left)
direction : 'ltr',
// speed for the flip transition in ms
speed : 1000,
// easing for the flip transition
easing : 'ease-in-out',
// if set to true, both the flipping page and the sides will have an overlay to simulate shadows
shadows : true,
// opacity value for the "shadow" on both sides (when the flipping page is over it)
// value : 0.1 - 1
shadowSides : 0.2,
// opacity value for the "shadow" on the flipping page (while it is flipping)
// value : 0.1 - 1
shadowFlip : 0.1,
// if we should show the first item after reaching the end
circular : false,
// if we want to specify a selector that triggers the next() function. example: ´#bb-nav-next´
nextEl : '',
// if we want to specify a selector that triggers the prev() function
prevEl : '',
// if we want to specify a selector to go to first
firstEl: '',
// if we want to specify a selector to go to last
lastEl: '',
// autoplay. If true it overwrites the circular option to true
autoplay : false,
// time (ms) between page switch, if autoplay is true
interval : 3000,
// callback after the flip transition
// old is the index of the previous item
// page is the current item´s index
// isLimit is true if the current page is the last one (or the first one)
onEndFlip : function(old, page, isLimit) { return false; },
// callback before the flip transition
// page is the current item´s index
onBeforeFlip : function(page) { return false; }
```

#### Vanilla usage example
```
const selector = document.querySelector("#bb-bookblock");
const bblock = new BookBlock(selector, {
	speed: 800,
	shadowSides: 0.8,
	shadowFlip: 0.7,
	nextEl: "#bb-nav-next",
	prevEl: "#bb-nav-prev",
	firstEl: "#bb-nav-first",
	lastEl: "#bb-nav-last"
});
```

#### jQuery usage example
```
$(function() {
			
	$( '#bb-bookblock' ).bookblock();

});
```

### Video
https://youtu.be/wiNtEos8tVU
