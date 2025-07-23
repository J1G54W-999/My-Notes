# HTML Attributes 
- HTML attributes are a way of adding additional information to you web page
- Some appears on the web page and some does not
- attributes can be added to any HTML element
- 
- Attributes are always coded INSIDE the opening tag of the HTML element
- Syntax: `Name of attribute = "value"` 
- ### Title Attribute:
- Provides extra info about an element
```
<p title="I am the tooltip popup!">Hover over this text for a tooltip popup.<p>
```
- ### Language Attribute:
- Declares the language of the website content
- You can specify a region if the language is spoken in different regions e.g. en-AU or en-US
```
<html lang="en-US">
```
#### NOTE: This does not change the language of the content, it just assists screen readers and SEO
- # HTML Lists:
- `<ol> </ol>`→Ordered lists (This is the boundary for the list)
- `<li> </li>`→List items (enter each item between these tags)
- ### Ordered Lists: Default
```
    <!DOCTYPE html>
<html>
    <head>
        <title>Tab Title goes here</title>
    </head>
    <body>
        <h1>This is an ordered list:</h1>
        <h3>Ratchet and Clank Games</h3>
        <ol>
            <li>Ratchet and Clank</li>
            <li>Ratchet and Clank 2: Going Commando</li>
            <li>Ratchet and Clank 3: Up Your Arsenal</li>
        </ol>
    </body>
</html>
```
- ### Ordered Lists: Different Numbering Types
- use `<ol type="I">` to change numbers into roman numerals
```
    <!DOCTYPE html>
<html>
    <head>
        <title>Tab Title goes here</title>
    </head>
    <body>
        <h1>This is an ordered list:</h1>
        <h3>Ratchet and Clank Games</h3>
        <ol type="I">
            <li>Ratchet and Clank</li>
            <li>Ratchet and Clank 2: Going Commando</li>
            <li>Ratchet and Clank 3: Up Your Arsenal</li>
        </ol>
    </body>
</html>
```
- ### Other types attributes for ordered lists:
- `type = "i"`→Lowercase roman numerals
- `type = "A"`→Uppercase letters
- `type = "a"`→Lowercase letters
- ### Unordered Lists: Default
```
    <!DOCTYPE html>
<html>
    <head>
        <title>Tab Title goes here</title>
    </head>
    <body>
        <h1>This is an unordered list:</h1>
        <h3>Best PS5 Games</h3>
        <ul>
            <li>God of War: Ragnarok</li>
            <li>Call of Duty: Modern Warfare 3</li>
            <li>Cyberpunk 2077</li>
        </ul>
    </body>
</html>
```
- ### Unordered Lists: Different Bullet Point Types
```
    <!DOCTYPE html>
<html>
    <head>
        <title>Tab Title goes here</title>
    </head>
    <body>
        <h1>This is an unordered list:</h1>
        <h3>Best PS5 Games</h3>
        <ul style="list-style-type: square;">
            <li>God of War: Ragnarok</li>
            <li>Call of Duty: Modern Warfare 3</li>
            <li>Cyberpunk 2077</li>
        </ul>
    </body>
</html>
```
- ### Other types attributes for unordered lists:
- `style="list-style-type:circle"`→Empty circle
- `style="list-style-type:square"`→Filled Square
- `style="list-style-type:none"`→Nothing
- ### Description Lists:
- Useful for adding extra info to your list items e.g. a restaurant menu
- `<dl> </dl>`→Description list boundary
- `<dt> </dt>`→Description list tag (for each item)
- `<dd> </dd>`→Each description tag description (extra info per item)
```
    <!DOCTYPE html>
<html>
    <head>
        <title>Tab Title goes here</title>
    </head>
    <body>
        <h1>HTML Description List:</h1>
        <h3>Basic Cyber Attack Descriptions</h3>
        <dl>
            <dt>Malware</dt>
            <dd>Viruses, worms, ransomware, and other malicious software designed to infect systems</dd>
            <dt>Phishing</dt>
            <dd>Deceptive emails designed to trick users into revealing sensitive information</dd>
            <dt>Ransomware</dt>
            <dd>Attacks that encrypt data and demand payment for its release</dd>
            <dt>SQL Injection</dt>
            <dd>Injecting malicious SQL code into a web applications input fiels to manipulate the database</dd>
        </dl>
    </body>
</html>
```
### Nested Lists:
- When you have multiple lists you want to display
```
    <!DOCTYPE html>
<html>
    <head>
        <title>Tab Title goes here</title>
    </head>
    <body>
        <h1>HTML Nested List:</h1>
        <h3>OG Anime Groups</h3>
        <ul>
            <li>One Piece</li>
            <ol>
                <li>Luffy</li>
                <li>Zoro</li>
                <li>Nami</li>
                <li>Usopp</li>
                <li>Sanji</li>
            </ol>
            <li>Black Clover</li>
            <ol>
                <li>Asta</li>
                <li>Yuno</li>
                <li>Noelle</li>
            </ol>
            <li>Demon Slayer</li>
            <ol>
                <li>Tanjuro</li>
                <li>Inosuke</li>
                <li>Zenitsu</li>
            </ol>
        </ul>
    </body>
</html>
```
