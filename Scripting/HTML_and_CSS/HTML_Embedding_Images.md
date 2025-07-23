# HTML Embedding Images
- The `<img>` tag does NOT have a closing tag
- This tag has 2 required attributes: >>1.
    1. `Src` attribute = link to the image
    2. `alt` attribute = Text to be read by screen readers (will also be displayed if image is not available)

- Syntax: `<img src="URL" alt="alternative text here">` 
- ### Absolute and Relative Images:
- `Absolute`= Points to an image on another website
- Must specify the location using the full http address, directory path and file name
- Example: `<img src="http://www.myclientweb page.com/images/clientprofilephoto.jpg">`  
- `Relative`= Points to an image in your own websites files
- Specify the path to the image in relation to the current file
- Example: `<img src="clientprofilephoto.jpg">`  
```
    <!DOCTYPE html>
<html>
    <head>
        <title>Client Web Page</title>
    </head>
    <body>
        <h1>Embed an image example</h1>

        <!--Example of an absolute url as src value-->
        <img
            src="https://vscodeedu.com/chip.png"
            alt="Computer chip"
        >

        <!--Example of a relative url as src value-->
        <img src="media/card-image.png" alt="Course image" >

        <!--Example of an error retrieving an image.-->
        <img src="error.jpg" alt="text here should describe the image." >
    </body>
</html>
```
#### NOTE: You can format `src` and `alt` on different lines for readability
- ### Sizing Images:
- Use the `height` and `width` attributes to size an image
- Syntax: `<img src="URL" alt="alternative text" Height="X" Width="Y"` 
- Example:
```
    <!DOCTYPE html>
<html>
    <head>
        <title>Client Web Page</title>
    </head>
    <body>
        <h1>Embed an image example</h1>
        <img 
            src="https://preview.redd.it/we-are-so-safe-v0-7wqaqmxnebbf1.jpeg?width=640&crop=smart&auto=webp&s=4062befdecedddcdb934f094ce7c48a9976783cb" 
            alt="the Visual Studio Code icon" width="600" height="400" 
        />
    </body>
</html>
```
