# CSS Display Property:
### Overview
- Specifies display behaviour of an element
- You can hide elements, remove them or make them behave like other elements etc.
- `inline`→Does NOT start on a new line and only takes up the horizontal space necessary
- Inline elements: `<a>` , `<img>` , `<button>` 
- `block-level`→starts on a new line and takes up the entire horizontal space
- Block-level elements: `<h1>` - `<h6>` , `<p>` , `<div>`
 
#### Syntax: `display: value;` 
---
### Common Display Elements:
1. `none` - Completely hide an element
2. `inline` - Displays an element on the same line with other elements
3. `block` - Makes an element take up the full width available
4. `inline-block` - Elements are displayed in a line, but respect
5. `flex` - Gives an element a flexible box layout (for when you change screen sizes)
6. `grid` - Displays the elements in a grid (rows and columns)
 ---
### Example: None
```
    <style>
    .hidden {
        display: none;
    }
</style>

<p class="hidden">This paragraph will not be displayed.</p>
```
 ---
### Example: Inline
```
    <button>Button 1</button> <button>Button 2</button> <button>Button 3</button>
```
 ---
### Example: Block
```
    <style>
    div {
        color: darkblue;
        background-color: yellow;
    }
</style>
    <div>Block element 1</div>

```
 ---
### Example: Inline-Block
```
    <body>
    <div style="display: inline-block; width: 100px; height: 100px; background-color: red;"></div>
    <div style="display: inline-block; width: 100px; height: 150px; background-color: blue;"></div>
    <div style="display: inline-block; width: 150px; height: 150px; background-color: green;"></div>
    <div style="display: inline-block; width: 75px; height: 100px; background-color: purple;"></div>
</body>
```
 ---
### Example: Flex
```
    <body>
    <div style="display: flex; justify-content: space-around;">
        <div>Item 1</div>
        <div>Item 2</div>
        <div>Item 3</div>
    </div>
</body>
```
 ---
### Example: Grid
```
    <body>
    <div style="display: grid; grid-template-columns: repeat(3, 1fr); grid-gap: 10px;">
        <div style="background-color: lightblue;">1</div>
        <div style="background-color: lightgreen;">2</div>
        <div style="background-color: lightcoral;">3</div>
        <div style="background-color: lightseagreen;">4</div>
        <div style="background-color: lightgrey;">5</div>
        <div style="background-color: lightpink;">6</div>
    </div>
</body>
```
