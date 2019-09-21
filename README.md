# frmwrk css

 Light weight CSS framework. This is currently a work in progress. You can browse the supported styles [here](https://soggybag.github.io/frmwrk-css/).

 ## Getting Started

 Download: 

 - `frmwrk.css`
 - `frmwrk-theme.css`

 Then add the following to the head of your HTML document. 

 ```html
<head>
  ...
  <link rel="stylesheet" href="frmwrk-theme.css">
  <link rel="stylesheet" href="frmwrk.css">
  ...
<head>
 ```

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

 ## Basic CSS styles 



 ## Web Components 

 Now includes web components! 
