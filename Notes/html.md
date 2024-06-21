# HTML Foundations

## Introduction to HTML
Hypertext Markup Language (HTML) is the raw data that you see when you look at something on the internet. **Cascading Style Sheets (CSS)** adds style to the HTML. **JavaScript (JS)** add interactivity/functionality to the HTML.

## Elements and Tags
* An HTML **element** is a piece of HTML wrapped in a tag.
* An HTML **tag** is used to represent the beginning and end of an HTML element.

## HTML Boilerplate
The HTML **boilerplate** is the basic structure for starting an HTML document.
* `<!DOCTYPE html>` tells the browser what version of HTML to use.
* `<html>` is the root element of an HTML document.
* `lang="en"` specifies the language of the HTML document.
* `<head>` contains meta information about the page.
* `<meta charset>` describes the character encoding used
* `<title>` specifies the title of the document.
* `<body>` contains all the content that will be displayed to the users.

### Example Boilerplate
```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>My First Webpage</title>
    </head>

    <body>
    </body>
</html>
```

### Viewing HTML files in the Browser
1. You can drag and drop an HTML file from your text editor into the address bar of your browser.

2. You can find the HTML file in your file system and then double click it. This will open up the file in the default browser your system uses.

3. You can use the terminal to open the file in your browser:
    * Navigate to the directory containing the file and type `open ./index.html`

### VSCode Shortcut
VSCode has a built-in shortcut you can use for generating all the boilerplate in one go. To trigger the shortcut, delete everything in the `index.html` file and just enter `!` on the first line.

## Working with Text
* `<p>` creates a paragraph
* `<h1>` - `<h6>` creates headings
* `<strong>` makes text bold
* `<em>` italicizes text
* Nesting elements creates parent, child, sibling relationships.
* `<!-- HTML Comment -->`
## Lists
* `<ul>` creates an unordered list
* `<ol>` creates an ordered list
* `<li>` creates a list item
## Links and Images
* `<a>` is an anchor element, used to create a link
* `href` is an attribute to add link to the anchor element
* To open a link in a new tab add `target="_blank"` to the anchor.
* The `rel` attribute is used to describe the relation between the current page and the linked document.
    * The `noopener` value prevents the opened link from gaining access to the webpage from which it was opened. 
    * The `noreferrer` value prevents the opened link from knowing which webpage or resource has a link (or ‘reference’) to it. 
    * It also includes the `noopener` behavior and thus can be used by itself as well.
* `<img>` is used to display an image
    * `src` attribute links to image
    * `alt` attribute describes the image
    * good idea to add image size attributes to all images
### Absolute and Relative Links
* Absolute links refer to other websites `protocol://domain/path`
* Relative links to other pages on your site and only include the file path to the other page relative to the page you are on.
### Parent Directories
* To go to the parent directory we need to use two dots in the relative filepath like this: `../`. 
## Commit Messages
* When writing code, it’s considered best practice to commit every time you have a meaningful change in the code.
* Effective commits consist of two separate parts: a subject, and a body.
    * The subject is a brief summary of the change you made to the project.
    * The body is a concise yet clear description of what you did.
# Intermediate HTML
# Advanced HTML