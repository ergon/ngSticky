Angular Sticky
==============
A fork on ngSticky !

### Chnages

  * Placeholder is cloned with opacity of 0



A simple, pure javascript (No jQuery required!) AngularJS directive to make elements stick when scrolling down.

### Features

  * Allows use of an offset so elements can be stuck to eg. 50px from the top of the browser
  * Recalculates element position on page load and on window resize
  * Clean: No external CSS or jQuery required, and it only adds the classes you specify.


### Bower

Install with bower:

```bash
bower install ngSticky
```


### Usage

Include the .js file in your page then enable usage of the directive by including the "sticky" module
as a dependency. Use the directive as follows:

```html
<div sticky> Hey there! </div>
```

To toggle the element stickiness you can bind with scope using the disabled-sticky (ng-model) as follows `{{ disabled = true }}`:

 ```html
    <div sticky disabled-sticky="disabled"> I won't stick! </div>
    <div sticky disabled-sticky="!disabled"> I will stick! </div>
 ```

To make the element stick within a certain offset of the top of the screen, you can provide an offset as follows:
```html
    <div sticky offset="100"> I won't touch the top of your screen! </div>
```
By default the element will be replaced with a place holder to prevent DOM resizing.  This can be disabled as follows:
```html
    <div sticky use-placeholder="false">I won't be replaced!</div>
```
If you want to customize the style while the element is sticky, we have an api for you too:
```html
    <div sticky offset="100" sticky-class="imSoSticky"> Taste my glue! </div>
```
And if you want to customize the body style while the element is sticky:
```html
    <div sticky offset="100" body-class="somethingIsSticky"> Taste my glue! </div>
```
And if you want to add in a class when the element is confined and bottomed out:
```html
    <div sticky offset="100" bottom-class="cantGoAnyFurther"> Taste my glue! </div>
```
It's also possible to set styles specifically for non sticky element:
```html
    <div sticky unsticky-class="container--unsticky"></div>
```
In order to enable sticky based on a media query:
```html
    <div sticky media-query="min-width: 768px"> Won't be sticky on small screens! </div>
```
If you want the sticky element to be scrollable only if it's smaller then the window inner height then you can set the `stick-limit` attribute:
```html
    <div sticky offset="100" stick-limit="true"> Will stick only if the element isn't bigger then the view</div>
```
And if you want to confine an element to its parent, and let it 'bottom out', just add the `confine` attribute:
```html
    <div sticky offset="100" confine="true"> Will unstick and stick to bottom of parent element</div>
```
> NOTE: The `confine` attribute will automagically assign its parent a `position: relative` style in order to help with absolute positioning relative to the parent.

If you'd like to use an element's overflow-y instead of the window scrollbar.  You can use the "sticky-scroll" element to denote an element styled to handle this.
```html
    <sticky-scroll style="overflow-y: scroll;min-height: 1000px;display: block;">
      <div sticky>Will stick to element, instead of window scrollbar.</div>
    </sticky-scroll>
```
> NOTE: This doesn't work for bottomed out or position absolute elements.


### Development

To start the development server:

```bash
npm run examples
// Then go to localhost:8080
```

To create the minified `dist/sticky.min.js` file, run:

```bash
npm run build
```


Cheers.
