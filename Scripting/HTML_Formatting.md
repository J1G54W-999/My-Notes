# HTML Formatting
### Basic Structure of a web page:
```
<!DOCTYPE html>
<html>
    <head>
        <title>Page Title</title>
    </head>

    <body>
        <h1>My First Heading</h1>
        <p>My first paragraph.</p>
    </body>
</html>
```
### Comments:
#### Syntax: `<!-- Your comment goes here -->` 
```
<!-- This is a multi-line comment
that will end on line 2 --> 

<!-- This line is commented out <p>This isn't visible on the web page</p> --> 
```
### Basic Opening and Closing Tags:
- `<!DOCTYPE html>`→Declaration use at the top of a file to indicate it is HTML
- `<html> </html>`→The beginning and end of the html section (same for all other tags)
- `<head> </head>`→Metadata about the website that is NOT displayed (info for search engines)
- `<title> </title>`→Specifies the title that appears in the browser's title bar or tab (required within the head section)
- `<body> </body>`→Where all of the content for the website lives

#### NOTE: Head and body order are like head and body of a person (head on top)
### Indentations:
- html does NOT need to be indented, but does make it easier to read

### Text Tags:
- `<h1> </h1>`→Heading tag (range is h1-h6)
```
<h1>Biggest heading here</h1>
<h2>Slightly smaller heading here</h2>
<h3>Keeps getting smaller</h3> 
```
- `<p> </p>`→Paragraph tags
```
<p>My first paragraph.</p>
<p>My second paragraph.</p>
<p>My third paragraph.</p>
```
# Nested Tags: Formatting
Nested tags go between other opening and closing tags

### Bold, Strong, Italics and Emphasise:
- `<b> </b>`→Bold tags 
```
<p><b>This text will be bold!</b></p>
```
- `<strong> </strong>`→Tells a screen reader the text should be emphasised because it is important (looks the same as bold)
```
<p><strong>This text is important!</strong></p>
```
#### NOTE: A screen reader is assistive technology that can turn text and images into audio or braille
 
- `<i> </i>`→Italics
```
<p><i>This text is italicised!</i></p>
```
- `<em> </em>`→Tells a screen reader the text should be emphasised (looks the same as italics)
```
<p><em>This text is emphasised!</em></p>
```
### Delete, Insert and Underline:
- `<del> </del>`→Makes text appear with a strikethrough  like it has been deleted
- `<u> </u>`→Underline text
- `<ins> </ins>`→shows inserted text, used mainly for updates and revisions (underlined by default)
```
<p>My favourite Anime is <del>Prison School</del> <ins>Dragonball Z!</ins> </p>
<p>The following word is <u>underlined</u></p>
```

### Small and Mark:
- `<small> </small>`→Makes the text appear smaller that the other text around it
- `<mark> </mark>`→Highlights text
```
<p>My cat is very <small>small</small>.</p>
<p>Remember to buy more <mark>cat food!</mark></p>
```
### Break and horizontal Line:
- `<br>`→Creates a line break like when you hit enter (has no closing tag)
- `<hr>`→Creates a horizontal line used as a separator (has no closing tag)
```
<p>This is a sentence on a line.<br>
This is on another line because of the line break above.</br>
There's a line break below this line from the the horizontal line tag.</p>
<hr>
```
