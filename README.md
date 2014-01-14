CanberraJS - Web Component and Polymer talk
=============================

## Web Components is an umbrella term for a set of draft [W3C specs](http://www.w3.org/TR/components-intro/)

1. ###[Templates](blob/master/Templates.md)

2. **HTML Imports**

3. **Custom Elements**

4. **Shadom DOM**




## Templates

New **&lt;template&gt;** element

DOM rather than String based template.

Like handlebars.js or other templates you already use, but native and standard.

```html
<template id=”tmpl”>
   <input type=”text” value=”{{obj.name}}”/>
</template>
```


## HTML Imports

Import components

```html
<link rel=”imports” href=”cat-movies.html”>
```


## Custom Elements

New **&lt;element&gt;** element:

Allows you to create new elements

```html
<element name=”my-special-btn”>
</element>

<my-special-btn />
```

Just like Angular directives (for 'E')

Must have a dash '-' in the name

New methods, properties, life-cycle callbacks

Nest script, style and template elements

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

Shadow DOM renders visually (and to AT) but cant be accessed by other CSS or Javascript*

Browser builders are already using it. e.g. HTML5 date input 


## Browser support 

Chromium canary - flags 
Firefox some
Safari – not yet
Android – not yet
Opera – not yet
IE … guess?







