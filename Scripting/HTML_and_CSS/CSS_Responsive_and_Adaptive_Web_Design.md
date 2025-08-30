# RWD (Responsive Design):

### Overview:
- Allows you to fluidly change and respond to the size of the user's screen
- The web page should look the same on a phone as it does on a laptop
- Uses `percentages` instead of hard-coded values
- `Fluid Grids`→layout that use relative units `percentages` instead of fixed units
- `Flexible Images`→Images that scale within their containing elements to fit different screen sizes
- `Media Queries`→CSS rules that allow content to adapt based on screen size and other device characteristics
 ---
#### Example: Fluid Grids
```
    <style>
    .container {
        width: 100%;
    }
    .column {
        float: left;
        width: 33.33%; /* 100% divided by 3 */
    }
</style>
```
--- 
#### Example: Flexible Images 
```
    <head>
    <style>
        img {
            max-width: 100%;
            height: auto;
        }
    </style>
</head>
<body>
    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRTnIPRWenW8WVhQf6xmqTucs9RdfFFoUeS4A&s" alt="IT Support meme" />
</body>
```
 ---
#### Example: Media Queries
```
    <style>
    @media (max-width: 600px) {
        body {
            background-color: lightblue;
        }
    }
    @media (min-width: 601px) and (max-width: 1024px) {
        body {
            background-color: lightgreen;
        }
    }
    @media (min-width: 1025px) {
        body {
            background-color: lightcoral;
        }
    }
</style>
```
#### NOTE: The screen should change colours depending on the screen size
---
## Adaptive Design:
 
- `Viewport`→The area on the web page visible to the user
- Control `viewport` via the `<meta>` tag

#### Example: Viewport
```
    <meta /> name="viewport" content="width-device-width", initial-scale="1.0">
```
 
- `Breakpoint`→The point in which a layout adapts (changes) based on the screen width of the device
- Control via `@media` queries by setting the width of the device
- You can set the default as normal and only specify when you want it to change
---
#### Example: Screen Sizes
```
    /* Tablet Devices */
@media (max-width: 768px)

/* Mobile Devices */
@media (max-width: 480px)

```
 ---
#### Example: Breakpoints
```
    <!DOCTYPE html>
<html>
    <head>
        <title>Adaptive Design Example</title>
        <style>
            body {
                font-family: Airal, sans-serif;
            }

            header,
            .content,
            footer {
                padding: 20px;
                text-align: center;
            }

            /* Default style for desktop */
            header {
                background-color: skyblue;
            }

            .content {
                background-color: lightgray;
            }

            footer {
                background-color: lightcoral;
            }

            /* Style for tablet devices */
            @media (max-width: 768px) {
                header {
                    background-color: lightgreen;
                }

                .content {
                    background-color: lightyellow;
                }

                footer {
                    background-color: lightblue;
                }
            }

                        /* Style for mobile devices */
            @media (max-width: 480px) {
                header,
                footer {
                    padding: 10px;
                    font-size: 14px;
                }

                .content {
                    background-color: lightpink;
                }

                .content p {
                    font-size: 12px;
                }
            }

        </style>
    </head>
    <body>
        <header>Website Header</header>
        <div class="content">
            <p>This it the content area. All of these colours will change depending on the screen size!</p>
        </div>
        <footer>Website Footer</footer>
    </body>

</html>
```
