CanberraJS - Web Component and Polymer talk
=============================

## Web Components is an umbrella term for a set of draft [W3C specs](http://www.w3.org/TR/components-intro/)

1. **Templates**

2. **HTML Imports**

3. **Custom Elements**

4. **Shadom DOM**




## Templates

New **&lt;template&gt;** element

DOM based template.


```html
<template id=”tmpl”>
   <input type=”text” value=”{{obj.name}}”/>
</template>
```

The HTML is parsed but any script wont run, images wont load until it is inserted into the document.

```javascript
var clone = document.importNode(document.getElementById('tmpl').content, true);
document.body.appendChild(clone);
```


## HTML Imports

Import components

```html
<link rel=”imports” href=”cat-movies.html”>
```

Access the content using the **.import** property.

```javascript
var content = document.querySelector('link[rel="import"]').import;
```

## Custom Elements



Allows you to create new elements using the new **&lt;element&gt;** element:

```html
<element name=”my-special-btn”>
</element>

<my-special-btn />
```

or script using **document.registerElement** 

```javascript
var mySpecialBtn = document.registerElement('my-special-btn');
document.body.appendChild(new mySpecialBtn());
```

There is also a callback API for the custom elements. For example when the element is inserted into the DOM.

```javascript
mySpecialBtn.attachedCallback = function() {
  ...
};
```

Kind of like Angular directives (for 'E')

Note: Custom elements must have a dash '-' in the name.


Elements can nest script, style and template elements.

```html
<element name=”my-special-btn”>
  <template>
  </template>
  <script>
  </script>
</element>
```


## Shadow DOM
Encapulates things in your element

*"Shadow DOM is an adjunct tree of DOM nodes. These shadow DOM subtrees can be associated with an element, but do not appear as child nodes of the element. Instead the subtrees form their own scope."* 
Shadow DOM Spec


Browser builders are already using it. e.g. HTML5 date input 


<input type="date"/>

## Browser support 

Chromium canary - flags 
Firefox some
Safari – not yet
Android – not yet
Opera – not yet
IE … guess?


# Enter Polymer
Platform.js is a polyfill for Web Components. Polymer adds an *opiniated* framework on top of Platform.js

Best to show an example [link to Geo-map]





