# CSS Positioning:

### Divisions:
- `<div> </div>` → A container element used to designate a division or section of you web page
- Goes within the `<body>` of your web page
- Web browsers by default will create a line break before and after a `<div>` 

#### Example: Containing Sections with Divs
```
    <!DOCTYPE html>
<html>
    <head>
        <title>CSS Layout</title>
        <style>
            div {
                color: aqua;
                background-color: brown;
            }
        </style>
    </head>
    <body>
        <h1>This heading is outside a division</h1>
        <div>
            <h3>This heading is contained inside a division</h3>
            <p>This paragraphs is contained insdie a division</p>
        </div>
        <p>This paragraph is outside a division</p>
    </body>
</html>
```
#### NOTE: The styling here will only affect the division area, but it affects both areas
---
### Class:
- A `class attribute`→An attribute that points to a class name in a styling sheet  
- Allows you to style multiple `<div> </div>` sections individually
- Needs to be written inside the opening tag of a HTML element
- Syntax: `<div class="class_name"` 
 
### How to use:
1. Add the classes you want to the style section of your code
2. Use the format `.class_name` 
3. Choose all of your styling options and how you want to apply them (font, colour etc.)
4. Add the class name inside the opening of your `<div>` tag
5. Done

### Example: Applying different `class` attributes to multiple `div` tags
```
    <!DOCTYPE html>
<html>
    <head>
        <title>This is outside the div</title>
        <style>
            .bright {
                color: yellow;
                background-color: aqua;
            }
            .dark {
                color: white;
                background-color: black;
            }
        </style>
    </head>
    <body>
        <h1>This heading is outside a div</h1>
            <div class="bright">
                <h3>This heading is inside a div</h3>
                <p>This paragraphs is inside a div</p>
            </div>
        <p>This paragraph is outside a div</p>
            <div class="dark">
                <h3>This heading is inside a div</h3>
                <p>This paragraphs is inside a div</p>
            </div>
    </body>
</html>
```
#### NOTE: You can add a class attribute to any HTML element in the opening tag
---
### The Box Model:
- Used to help visualise padding, margins and elements
- These are what contain the contents of each element

### Example: A Visual of the Box Model
```
    <!DOCTYPE html>
<html>
    <head>
        <title>CSS Box Model</title>
        <style>
            div {
                border: solid 5px;
                width: 100px; 
                height: 25px;
                padding: 25px;
                margin: 30px;
            }
        </style>
    </head>
    <body>
        <h3>Below is an example of the box model</h3>
        <div>This is a box!</div>
        <p>Above is a simple example of the box model</p>
    </body>
</html>
```

## CSS Positioning Types CSS:

#### The 5 Position Types:
1. `Static` = Default
2. `Relative` = Default + Alterations
3. `Absolute` = Based of Ancestor
4. `Fixed` = Doesn't move (Even when scrolling)
5. `Sticky` = Relative > fixed (once threshold is passed)

### Static:
- Is the default positioning for elements
- Elements are positioned according to the flow of your HTML document
- Elements are NOT affected by the top, bottom, left, right properties

#### Example: Static Positioning
```
    <div style="position: static;">This is a static positioned element.</div>
```

### Relative: 
- The element is positioned relative to its default position
- Elements ARE affected by the top, bottom, left, right properties
 
#### Example: Relative Positioning
```
    <div style="position: relative; left: 20px; top: 10px;">This is a relatively positioned element.</div>
```
 
### Absolute:
- The element is positioned relative to its closest positioned ancestor
- Elements ARE affected by the top, bottom, left, right properties based on its ancestor
- `Ancestor`→The outer element of  another element
- `Parent`→An ancestor with only ONE level of nesting
- `Descendant`→An element inside another element
 
#### Example: Absolute Positioning
```
    <div style="position: absolute; top: 30px; left: 40px;">This is an absolutely positioned element.</div>
```
 
### Fixed:
- The element will always stay in the same place (even when the user is scrolling)
- Used for navigation bars or footers

#### Example: Fixed Positioning
```
    <div style="position: fixed; bottom: 0; right: 0;">This is a fixed positioned element.</div>
```
 
### Sticky:
- The element is treated like a relative positioned element until it crosses a specific point
- Goes from relative > fixed
- You can stick it to the top of bottom of a page, so when the user scrolls, it sticks!
 
#### Example: Sticky Positioning
```
    <div style="position: sticky; top: 0;">This is a sticky positioned element.</div>
```
