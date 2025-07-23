# Styling Links, Images and Favicons
### Types of Links:
 
#### Absolute Links:
- A full URL that links to a page on ANOTHER website
- Example: `<a href="https://www.youtube.com/shorts/swQRnW561BA">The URL will become a clickable link here</a>` 

#### Relative Links:
- A link that points to another place on the CURRENT website
- Example: `href="index.html"` 

### Opening Links
- When you click a hyperlink it will open in the same tab by default
- To open the link in a new tab you can add the `target="_blank"` attribute after the link
- Example: `This will open the <a href="https://bit.ly/cyber-meme" target="_blank"> link </a> in a new tab` 
![](https://remnote-user-data.s3.amazonaws.com/SScpv2bak-CS1JCn4wFQZnJynOTAnrmFVx1fO0GOa4BqsmVgAy5xts-7cqCqYaNerc0O9f-qFcHAobiaK_u5YMZMTf-JxBRqO_S5nRi9zJ3JhE5AQu5baTCobqaOWKyF.png)

---
### Styling Links:

#### By default, links will do the following:
1. The text of all links appear as underlined
2. The text of 'unvisited' links will appear blue
3. The moment a user clicks on a link the text of the 'active' link will appear red
4. Once you have 'visited' a link, the text will appear purple
 
#### Example: Change how a link is interacted with
```
    <!DOCTYPE html>
<html>
    <head>
        <style>
            a:link {
                color: red;
                background-color: transparent;
                text-decoration: underline;
            }
            a:hover {
                color: green;
                background-color: blue;
                text-decoration: none;
            }
            a:active {
                color: yellow;
                background-color: purple;
                text-decoration: none;
            }
            a:visited {
                color: pink;
                background-color: transparent;
                text-decoration: underline;
            }
        </style>
    </head>

    <body>
        <a href="https://microsoft.com" target="_blank">Visit one of my favorite websites!</a>
    </body>
</html>
```
---
### Images as Links:
- To use an image as a link, put the `<img>` tag inside of the `<a>` tag

#### Example: Using an image as a link
```
    <a href="https://chess.com">
<img src="queen.png" alt="the Microsoft logo"style="width:440px;height:440px;">
Visit one of my favorite websites!</a>
```
 
### Email as Links:
- Use the `mailto:` attribute and the recipients email address
- This will open up the user's default email and prefill the recipients email address

#### Example: Using a link to send an email
```
<body>
    <h1>Send an email with this link:</h1>
    <a href="mailto:person@email.com">Write to me!</a>
    <p>When this link is clicked it will open the user's default email with the recipient already addresses<p>
</body>
```
---
### Favicons:
- The small icon at the top of tabs
- Use the `.ico` or `.png` extensions
- Use the `<link>` tag
- `href` = link to your image you want to use
- `rel` = relationship
- `type` = MIME Type (usually `image/x-icon` for `.ico`  or `image/png` for `.png` files)

#### Example: How to link a favicon.ico
```
    <head>
    <title>This tab has a favicon!</title>
    <link rel="icon" type="image/x-icon" href="/images/favicon.ico">
</head> 
```
---
### Image Borders:
- Use the `<style> </style>` tags to edit the border of an image
- Place an `<img>` tag inside and add your modifications
- Tags inside the `<style> </style>` tags don't use `< >` and use `{ }` as boundaries
```
    <!DOCTYPE html>
<html>
    <head>
        <title>Image Border Styling</title>
            <style>
                img {
                    border-width: 3px;
                    border-style: dotted;
                    border-color: green;
                    border-radius: 25px;
                    width: 200px;
                    height: 200px;
                }
            </style>
    </head>
    <body>
        <img src="portrait.jpg" alt="Sample Image" />
    </body>
</html>
```
---
### HTML Span Tags:
- `<span> </span>` tags are generic inline container elements
- Used to 'wrap' sections of text
- Allows you to modify the styling of a section or word without creating a new line of content
- Span tags override default style settings, so you can change individual sections without affecting other sections
- 
- ### Example: Changing two sections within a sentence
```
    <!DOCTYPE html>
<head>
    <title>HTML Span Tags</title>
    <style>
        p {
            color: blue;
            font-size: 14px;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <h1>HTML Span Tags</h1>
    <p>Come to our event on <span style="color: red; font-style: italic;">March 30, 2025</span> and 
        help us keep out neighborhood <span style="color: green; font-style: italic;">green</span>. 
        See you there!
    </p>
</body>
```
