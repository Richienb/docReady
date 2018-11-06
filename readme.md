# docready

## Summary

docReady is a single plain javascript function that provides a method of 
scheduling one or more javascript functions to run at some later
point when the DOM has finished loading.

It works similarly to [jQuery](https://jquery.com/)'s `$(document).ready()`, but this is a small
single standalone function that does not require jQuery in any way.

## Examples

These are various forms of usage:

```js
// pass a function reference
docReady(fn);
```

```js
// use an anonymous function
docReady(function() {
    // code here
});
```

```js
// pass a function reference and a context
// the context will be passed to the function as the first argument
docReady(fn, context);
```

```js
// use an anonymous function with a context
docReady(function(ctx) {
    // code here that can use the context argument that was passed to docReady
}, context);
```

## Side notes

docReady(fn) can be called as many times as desired and each callback function will be
called in order when the DOM is done being parsed and is ready for manipulation.

If you call docReady(fn) after the DOM is already ready, the callback with be executed
as soon as the current thread of execution finishes by using setTimeout(fn, 1).

## Browser compatibility

It has been tested in the following browser configurations:

- IE6 and up
- Firefox 3.6 and up
- Chrome 14 and up
- Safari 5.1 and up
- Opera 11.6 and up
- Multiple iOS devices
- Multiple Android devices

## Usage

Simply load the script via a script tag:

```html
<script src="https://cdn.jsdelivr.net/gh/jfriend00/docReady@master/docready.min.js"></script>
```

Other discussions can be found [here](http://stackoverflow.com/questions/9899372/pure-javascript-equivalent-to-jquerys-ready-how-to-call-a-function-when-the/9899701#9899701).
