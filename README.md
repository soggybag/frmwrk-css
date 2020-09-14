# frmwrk css

 Light weight CSS framework. This is currently a work in progress. You can browse the supported styles [here](https://soggybag.github.io/frmwrk-css/).

 ## Getting Started

 Download: 

 - [`frmwrk.css`](https://raw.githubusercontent.com/soggybag/frmwrk-css/master/frmwrk.css)
 - [`frmwrk-theme.css`](https://raw.githubusercontent.com/soggybag/frmwrk-css/master/frmwrk-theme.css)

 Then add the following to the head of your HTML document. 

 ```html
<head>
  ...
  <link rel="stylesheet" href="frmwrk-theme.css">
  <link rel="stylesheet" href="frmwrk.css">
  ...
<head>
 ```

## Get the files from github.io 

https://soggybag.github.io/frmwrk-css/frmwrk.css


## Layout

Frmwrk doesn't provide any layout or grid system. These tasks are best handeled with [CSS Grid](https://css-tricks.com/snippets/css/complete-guide-grid/).

## Navbar 

Navbars can be created easily by creating a parent element with the class name `navbar`. 

```
html<div class="navbar">
  <ul>
    <li><h1 class="title">TITLE</h1></li>
    <li><a href="#">Link 1</a></li>
    <li><a href="#">Link 2</a></li>
    <li><a href="#">Link 3</a></li>
    <li><a href="#">Link 4</a></li>
  </ul>
</div>
```

A list of links will lay itself out automatically. 

## Footers 

You can easily create a footer using the class name `page-footer`. 

```html
<div class="page-footer">
  <ul>
    <li><h3>Column 1</h3></li>
    <li><a>Item 1</a></li>
    <li><a>Item 2</a></li>
    <li><a>Item 3</a></li>
  </ul>
  
  <ul>
    <li><h3>Column 2</h3></li>
    <li><a>Item 1</a></li>
    <li><a>Item 2</a></li>
    <li><a>Item 3</a></li>
  </ul>
  
  <ul>
    <li><h3>Column 3</h3></li>
    <li><a>Item 1</a></li>
    <li><a>Item 2</a></li>
    <li><a>Item 3</a></li>
  </ul>
</div>
```

Child elements in the footer will automatically layout with Flex box centered. 

 ## Todo: 

 - Add documentation 
 - Add alternate themes 
 - Add some form styles
  - Grouping options for form elements (see: https://purecss.io/forms/ for ideas)
    - Inline
    - Stacked
    - Grouped 
 - Better organize scss and css files
 - Add sass build script
  - Add minification
  - https://github.com/hellobrian/sass-recipes/tree/master/node-sass
  - https://stackoverflow.com/questions/40579330/minify-css-with-node-sass

 ## Web Components 

Coming soon web components! 
