# JavaScript

`JavaScript`→Adds interactivity and other advanced behaviours to web pages

Features:
    - Enables Interactivity e.g. Drop-down menus
    - Real-time interaction
    - Runs code on the client-side rather than server-side
    - Works across all modern web browsers
    - Many pre-written frameworks and libraries
 
 ---
### How to use JavaScript:
```
<script>
    // Your JavaScript code goes here!
</script> 
```
### NOTE: you must place your code between the `<script>` tags
 ---
 #### Example: Importing `JavaScript` 
```
<script> src="my_javascript_file.js" </script>
```
#### NOTE: This works the same way as external CSS
--- 
### `Alert` Function:
- An alert will create a pop-up on the web page when opened
 
#### Example: `Alert` Function
```
<script>
    alert("You've been hacked!")
</script> 
```
#### NOTE: You will have to refresh the code each time to run it this way
 ---
### Basic Button:
#### Syntax: 
`<button type="value">This text appears on the button</button>`

#### Example: Basic `button` 
```
// This is a clickable button
<button type="button">Click Me!</button>
```
#### NOTE: You can also style the button with CSS
  ---
 ### HTML Event Attributes:
 
Specifies how elements should behave in response to certain events i.e. clicking on an element
 
#### Syntax:
`<element attribute name="value"></element>` 
 
### `onClick` Attribute:
 
#### Example: HTML `OnClick` event attribute
```
<element onClick="script"></element>
```
#### NOTE: The value of `script` is what will be executed when the button is clicked
--- 
### Modifying HTML with JavaScript:
 
`innerHTML` attribute→Directly modifies the HTML content within an HTML element.
`getElementByID()` function→A JavaScript function that returns the element with the specified ID
 
#### Example: 
```
    <!DOCTYPE html>
<body>
    <p id="Text_ID">Hello World!</p>
    <button id="Button_ID">Click Me!</button>

    <script>
        document.getElementById('Button_ID').onclick = function() {
            document.getElementById('Text_ID').innerHTML = ':)';
        };
    </script>
</body>
</html>
```
 
#### Explanation:
- Above we have the HTML elements of some text and a button
- The JavaScript links to these elements via IDs ( `Text_ID` for the text and `Button_ID` for the button)
- The `onclick` property is assigned a function, which is defined between the curly braces `{ }` 
- In this case, the function updates the `innerHTML` of the paragraph linked to `Text_ID` 
--- 
## Triggering Functions:
 
- You can `trigger built-in JavaScript` functions like pop-ups with an HTML attribute
- You can use a button to trigger a script when clicked

#### Example: Triggering `alert function`  
```
<button onClick="alert('You have been hacked!)">Click Me!</button>
```
 ---
### Triggering Custom Functions:
- You can create `custom functions` and set them to trigger when a button is clicked
- Everything between the `{ }` is part of the function and will be executed
 
#### Example: 
```
    <!DOCTYPE html>

<button onclick="boring_popup()">Click me!</button>

<script>
    function greeting() {
        alert('This is another pop-up');
    }
</script>
```
#### NOTE: You can make a way more advanced function here instead
