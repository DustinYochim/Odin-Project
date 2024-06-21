# CSS Foundations

## Intro to CSS
CSS is what adds style to the plain HTML elements on a page.

### Basic Syntax
At the most basic level, CSS is made up of various rules. These rules are made up of a selector and a semicolon-separated list of declarations, with each of those declarations being made up of a property-value pair.
```css
div.bold-text {
    font-weight: 700;
}
```
### Selectors
Selectors refer to the HTML elements to which the CSS rules are being applied to.

#### Universal Selector
The universal selector will select elements of any type.
```css
* {
    color: purple;
}
```
#### Type Selector
The type selector selects all elements of a given type.
```css
div {
    color: white;
}
```

#### Class Selector
The class selector selects elements with a given class.

```css
.alert-text {
    color: red;
}
```

#### ID Selector
ID selectors select elements with a given ID.

```css
#title {
    background-color: red;
}
```

#### Grouping Selectors

You can group selectors together using a `,`.

```css
.read,
.unread {
    color: white;
    background-color: black;
}
```

#### Chaining Selectors
You can chain selectors together to only select elements that have all the given rules.
```css
.subsection.header {
    color: red;
}
```

#### Descendant Combinator
Combinators allow us to combine multiple selectors differently than either grouping or chaining them, as they show a relationship between the selectors.

A descendant combinator will only cause elements that match the last selector to be selected if they also have an ancestor (parent, grandparent, etc.) that matches the previous selector.

```css
.ancestor .contents {
  /* some declarations */
}
```

### Basic CSS Properties

#### Color and Background Color
The `color` property sets an element's text color, while the `background-color` sets the background color of an element. Properties that expect a color value can accept keywords, HEX, RGB, and HSL values.
```css
p {
    color: #1100ff;
}

p {
    color: rgb(100, 0, 127);
}

p {
    background-color: black;
}
```
#### Typography Basics and Text-Align
* `font-family` can be a single value or a comma-separated list of values that determine what font an element uses.
* `font-size` sets the size of the font.
* `font-weight` sets the boldness of the text.
* `text-align` will align text horizontally within an element.

#### Image Height and Width
By default, an `<img>` element’s `height` and `width` values will be the same as the actual image file’s height and width. If you wanted to adjust the size of the image without causing it to lose its proportions, you would use a value of `auto` for the `height` property and adjust the `width` value.
```css
img {
    height: auto;
    width: 500px;
}
```
You should include height and width values both in the HTML and the CSS to prevent drastic shifts when the page loads.

### Adding CSS to HTML
You can name the `.css` file whatever you want as long as the file type is `.css`, though `style` or `styles` is most commonly used.
#### External CSS
External CSS involves creating a separate file for the CSS and linking to it inside of an HTML's opening and closing `<head>` tags with a self-closing `<link>` element.
```html
<head>
    <link rel="stylesheet" href="styles.css">
</head>
```
The pros of this method are:
1. It keeps the HTML and CSS separated, which results in the HTML file being smaller and easier to look at.
2. You only need to edit the CSS in one place.

#### Internal CSS
Internal CSS (or embedded CSS) involves adding the CSS within the HTML file itself instead of creating a completely separate file.
```html
<head>
    <style>
        div {
            color: white;
            background-color: black;
        }
    </style>
</head>
<body>
</body>
```

This method can be useful for adding unique styles to a single page of a website, but it doesn’t keep things separate like the external method, and depending on how many rules and declarations there are it can cause the HTML file to get pretty big.

#### Inline CSS
Inline CSS makes it possible to add styles directly to HTML elements, though this method isn’t as recommended.
```html
<body>
  <div style="color: white; background-color: black;">...</div>
</body>
```

## The Cascade
The CSS cascade is a concept in CSS that determines how styles are applied to elements on a web page when multiple rules could potentially apply to the same element. The cascade involves the combination of different sources of stylesheets, their specificity, and the order in which they appear.

### Sources of Styles

There are three primary sources of CSS styles:
* **Author stylesheets**: CSS defined by the developer within the HTML document or linked CSS files.
* **User stylesheets**: CSS defined by the user, usually in their browser settings.
* **User-agent stylesheets**: Default styles provided by the browser.

The order of priority is usually:

1. User stylesheets
2. Author stylesheets
3. User-agent stylesheets

However, user stylesheets can be overridden by author stylesheets if the `!important` rule is used.

### Specificity

Specificity determines which CSS rule is more specific and thus should be applied. Specificity is calculated based on the types of selectors used:
* Inline styles have the highest specificity.
* ID selectors have high specificity.
* Class selectors, attribute selectors, and pseudo-classes have medium specificity.
* Element selectors and pseudo-elements have low specificity.

The more specific the selector, the higher its priority in the cascade.

### Importance

The `!important` declaration can be used to override any other declarations, regardless of specificity or source.

### Order of Appearance
When two rules have the same specificity and importance, the one that appears last in the CSS (or the last linked stylesheet) will be applied. This is known as the “last declaration wins” rule.

### Summary
When the browser encounters conflicting CSS rules, it resolves the conflict by following these steps:
1. Origin of Styles: Determine the source (user, author, user-agent).
2. Importance: Consider !important declarations.
3. Specificity: Calculate specificity of each rule.
4. Order: If all else is equal, apply the rule that comes last.

## Inspecting HTML and CSS

### The Inspector
To open up the inspector, you can right-click on any element of a webpage and click “Inspect” or press F12.

### Inspecting Elements
In the Elements panel, you can see the entire HTML structure of your page. You can click on any of the elements in this panel to select that specific element.

When an element is selected, the Styles tab will show all the currently applied styles, as well as any styles that are being overwritten (indicated by a strikethrough of the text).

### Testing Styles in the Inspector
The Styles panel also allows you to edit styles directly in the browser. You can click inside of any individual selector to add a new rule or click on an existing attribute or value to alter it. 

## The Box Model
Every single thing on a webpage is a rectangular box. These boxes can have other boxes in them and can sit alongside one another. You can get a rough idea of how this works by applying an outline to every element on the page.
```css
* {
    outline: 2px solid red;
}
```

### Box Model Components
1. **Content**: The innermost part where the text and images appear.
2. **Padding**: Space between the content and the border. It is transparent.
3. **Border**: The area surrounding the padding (if any) and the content. It can have color and style.
4. **Margin**: The outermost space between the border and other elements. It is also transparent.

```
+---------------------------------------+
|               Margin                  |
|  +---------------------------------+  |
|  |            Border               |  |
|  |  +---------------------------+  |  |
|  |  |         Padding           |  |  |
|  |  |  +---------------------+  |  |  |
|  |  |  |      Content        |  |  |  |
|  |  |  +---------------------+  |  |  |
|  |  +---------------------------+  |  |
|  +---------------------------------+  |
+---------------------------------------+
```

CSS Properties to adjust areas of the box model:
* Content
    * `width` and `height`
* Padding
    * `padding`
* Border
    * `border-width`, `border-style`, `border-color`
* Margin
    * `margin`
* **Box Sizing**
    * The default behavior is content-box where the `width` and `height` properties apply to the content box only.
    * Setting `box-sizing: border-box` makes the `width` and `height` apply to the content, padding, and border and simplifies the management of element size.

## Block and Inline
CSS has two box types: block and inline boxes, which determine element behavior and interaction. The display property controls how HTML elements appear on the webpage.

### Block vs Inline
By default, block elements will appear on the page stacked atop each other, each new element starting on a new line.

Inline elements, however, do not start on a new line. They appear in line with whatever elements they are placed beside.

Inline-block elements behave like inline elements, but with block-style padding and margin.

### Divs and Spans
Divs and spans give no particular meaning to their content. They are just generic boxes that can contain anything.

Div is a block-level element by default. It is commonly used as a container element to group other elements. Divs allow us to divide the page into different blocks and apply styling to those blocks.

Div is a block-level element by default. It is commonly used as a container element to group other elements. Divs allow us to divide the page into different blocks and apply styling to those blocks.

## Flexbox
Flexbox is a way to arrange items into rows or columns. These items will flex (i.e. grow or shrink) based on some rules that you can define.

### Flex Container Properties

1. `display`
    * `flex`: Establishes a flex container.
	* `inline-flex`: Creates an inline flex container.
2. `flex-direction`
	* `row`: Default. Items are placed in a row (left to right).
	* `row-reverse`: Items are placed in a row (right to left).
	*	`column`: Items are placed in a column (top to bottom).
	*	`column-reverse`: Items are placed in a column (bottom to top).
3.	`flex-wrap`
	* `nowrap`: Default. All items are on one line.
	* `wrap`: Items will wrap onto multiple lines.
	* `wrap-reverse`: Items will wrap onto multiple lines from bottom to top.
4.	`flex-flow`
	* Shorthand for `flex-direction` and `flex-wrap`.
	* Example: `flex-flow: row wrap;`
5.	`justify-content`
	* `flex-start`: Default. Items are packed toward the start.
	* `flex-end`: Items are packed toward the end.
	* `center`: Items are centered along the line.
	* `space-between`: Items are evenly distributed; first item is at the start, last item is at the end.
	* `space-around`: Items are evenly distributed with space around them.
	* `space-evenly`: Items are evenly distributed with equal space around them.
6.	`align-items`
	* `stretch`: Default. Items stretch to fill the container.
	* `flex-start`: Items are aligned at the start.
	* `flex-end`: Items are aligned at the end.
	* `center`: Items are centered.
	* `baseline`: Items are aligned along their baseline.
7.	`align-content`
	* `stretch`: Default. Lines stretch to fill the container.
	* `flex-start`: Lines are packed at the start.
	* `flex-end`: Lines are packed at the end.
	* `center`: Lines are centered.
	* `space-between`: Lines are evenly distributed; first line is at the start, last line is at the end.
	* `space-around`: Lines are evenly distributed with space around them.
	* `space-evenly`: Lines are evenly distributed with equal space around them.

### Flex Item Properties

1. `order`
	* Default is 0. Controls the order of items.
2. `flex-grow`
	* Default is 0. Defines the ability for an item to grow if necessary.
3.	`flex-shrink`
	* Default is 1. Defines the ability for an item to shrink if necessary.
4. `flex-basis`
	* Default is auto. Defines the default size of an element before the remaining space is distributed.
5.	`flex`
	* Shorthand for `flex-grow`, `flex-shrink`, and `flex-basis`.
	* Example: `flex: 1 1 auto;`
6.	`align-self`
	* `auto`: Default. Inherits from the parent `align-items`.
	* `flex-start`: Aligns the item at the start.
	* `flex-end`: Aligns the item at the end.
	* `center`: Centers the item.
	* `baseline`: Aligns the item along its baseline.
	* `stretch`: Stretches the item to fill the container.