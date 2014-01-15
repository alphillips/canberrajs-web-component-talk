CanberraJS - Web Component and Polymer talk
=============================

![alt text](http://www.polymer-project.org/images/logos/webcomponents.png "Web Components")


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

Lifecycle and callback API for custom elements. 
For example when the element is inserted into the DOM.

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
Encapsulates things in your element. 
Keep content in the normal DOM but the div spaghetti in the shadow DOM.

*"Shadow DOM is an adjunct tree of DOM nodes. These shadow DOM subtrees can be associated with an element, but do not appear as child nodes of the element. Instead the subtrees form their own scope."* 
Shadow DOM Spec

```javascript
var host = document.querySelector('#id');
var root = host.createShadowRoot();
root.innerHTML = '<div>spaghetti</div>';
```

Browser developers are already using it. e.g.  [HTML5 date input](http://www.wufoo.com/html5/types/4-date.html)



## Browser support 

1. Chrome - some
2. Firefox - some
3. Safari – no
4. Android – no
5. Opera – no
6. IE - lol

[Check browser compatability](http://jonrimmer.github.io/are-we-componentized-yet/)

# Enter Polymer
[Platform.js](https://github.com/Polymer/platform) is a polyfill for Web Components. 
[Polymer](http://www.polymer-project.org/) adds an *opinionated* framework on top of Platform.js

Best to show an [example](https://github.com/alphillips/geo-map).





