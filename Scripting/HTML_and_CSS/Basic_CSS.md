# Basic CSS
- `CSS` → Cascading Style Sheet 
- If HTML is the basic structure of a house, CSS is the interior design
### Cascading Order: Priority
1. `Inline styles` have the highest priority (applied last)
2. `Internal styles` within the `<style>` tag (applied third) 
3. `External stylesheets` (applied second)
4. `Browser default styles` (applied first)
- NOTE: These styles are APPLIED from the bottom-up, but PRIORITISED from top-down. So Inline styles override all other styles and internal styles overrides external styles
### Inline CSS:
- When the `style` is written INSIDE the opening HTML tag you are styling
- Syntax: `style="property:value;"` 
- property = colour, font etc.
- value = setting of those properties
#### Example: `style="width:400px; height:600px;"` 
- `:` as a separator
- `;` at the end of the value
- ### Example: Sizing Images with CSS
```
    <!DOCTYPE html>
    <head></head>
    <body>
        <h1>Embed an image example</h1>
        <img src="boring_image.jpg" alt="image of something boring" style="width:400px; height:600px;">
    </body>
</html>
```
# Basic CSS Properties:
- `font-size`→`style="font-size:36px;"` 
#### Example: Different Font Sizes with CSS
```
    <!DOCTYPE html>
<html>
    <head>
        <Title>Browser Tab Title</Title>
    </head>
    <body>
        <p style="font-size:36px;">This is some random text, make me 36px!</p>
        <p style="font-size:24px;">This is some random text, make me 24px!</p>
        <p style="font-size:12px;">This is some random text, make me 12px!</p>
    </body>
</html>
```
---
- `font-family`→`style="font-family:Arial;"` 
#### Example: Different Fonts with CSS
```
    <!DOCTYPE html>
<html>
    <head>
        <Title>Browser Tab Title</Title>
    </head>
    <body>
        <p style="font-family:Arial;">This text is in Arial!</p>
        <p style="font-family:Times New Roman;">This is Times New Roman!</p>
        <p style="font-family:Courier New;">This text is in Courier New!</p>
    </body>
</html>
```
- You should set a FALLBACK if the font isn't available for the browser being used
- Each font will be tried, if all fails then any `serif` font will be used
```
<p style="font-family:Times New Roman, Times, serif;">Fallback fonts!</p>
```
---
- `color`→`style="color:blueviolet;" ` 
#### Example: Different Colours with CSS
```
    <!DOCTYPE html>
<html>
    <head>
        <title>Browser Tab Title</title>
    </head>
    <body>
        <p style="color:blueviolet;">BLUEVIOLET</p>
        <p style="color:aquamarine;">AQUAMARINE</p>
        <p style="color:green;">GREEN</p>
        <p style="color:blue;">BLUE</p>
    </body>
</html>
```
#### NOTE: Colour has to be spelled color in HTML and CSS
---
### Background:
- Used for setting the background COLOUR or IMAGE of an  HTML element
- `background colour`→`style="background:red;"` 
#### Example: Background Text Colour with CSS
```
    <!DOCTYPE html>
<html>
    <head>
        <title>Browser Tab Title</title>
    </head>
    <body>
        <p style="background:red;color:blueviolet;">BLUEVIOLET</p>
        <p style="background:pink;color:aquamarine;">AQUAMARINE</p>
        <p style="background:orange;color:green;">GREEN</p>
        <p style="background:gray;color:blue;">BLUE</p>
    </body>
</html>
```
#### Example: Background of Web Page Colour
```
    <!DOCTYPE html>
<html>
    <head>
        <title>Background Colour</title>
    </head>
    <body style="background:grey;">
        <h1>Changing Web Page Colour:</h1>
        <p>The background of this page is now grey, as it is in the body tag</p>
    </body>
</html>
```
--- 
### Internal CSS:

- `Internal CSS` or `Embedded CSS`→Written within the `<head>` section of an HTML document
- Applies styles to that specific document only

#### Syntax: `<head style="property:value">` 
#### Example: Styling all paragraphs the same
```
    <!DOCTYPE html>
<html>
    <head>
        <style>
            body {
                background-image: url("image.png");
                background-size: cover;
                background-position: center;
            }
           h1 {
                color: aquamarine;
            }
           p {
                color:blueviolet;
                font-size:20px;
            }
        </style>
    </head>
    <body>
        <h1>Internal CSS:</h1>
        <p>Internal CSS uses style tags within the head tags</p>
        <p>You musty specify each section without the &lt; &gt; tags</p>
        <p>The formatting uses curly brackets { } as boundaries</p>
        <p>Each section needs to have its own curly brackets { }</p>
    </body>
</html>
```
#### NOTE: Internal CSS uses curly brackets as boundaries for each section and does NOT use `< >` tags to specify the name of the section like it normally does
---
### External CSS:
- External CSS is written as a separate file that is linked to the HTML documents you want to style

#### How to use:
1. Create a file with the .css extension
2. Add all of the styling options you want inside of the file
3. Link it inside of the `<head>` section of the document you want to style with the `<link>` tag
4. Done
#### NOTE: The `<link>` tag has no closing tag

### Example: Applying External CSS
```
    <!DOCTYPE html>
<html>
    <head>
        <link rel="stylesheet" href="style.css" />
    </head>
    <body> </body>
</html>
```
- `rel`→Specifies the relationship between the current document and the linked document
- `href`→Specifies the URL of a hyperlink
