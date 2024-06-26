# JavaScript Basics
JavaScript can be used to make a website interactive. It can be run via the browser or in an outside environment. You can either include your javascript directly in your HTML file or link to it in an external script.
```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Page Title</title>
</head>
<body>
  <script>
    // Your JavaScript goes here!
    console.log("Hello, World!")
  </script>
</body>
</html>
```
```javascript
<script src="javascript.js"></script>
```

## Variables and Operators
### Variables
A variable is like a "storage container" for data in your code.

You can declare variables to store data by using the `var`, `let`, or `const` keywords.
* `let` - is a modern variable declaration
* `var` - is an old-school variable declaration (not normally used anymore)
* `const` - is like `let`, but the value of the variable can't be changed.

* Variable names must contain only letters, digits, or `$` and `_`.
    * Combine multiple words using camelCase
    * Name familiar constants as UPPERCASE_CONSTANTS


### Numbers
* Arithmetic operators perform arithmetic on numbers (literals or variables).
* JavaScript arithmetic operators include: `+`, `-`, `*`, `**`, `/`, `%`, `++`, and `--`.
* The numbers (in an arithmetic operation) are called **operands**. The operation (to be performed between the two operands) is defined by an **operator**.
* Operator precedence is PEMDAS.
* `10 + 20 = 30`, `"10" + "20" = "1020"`, `10 + "20" = "1020"
* `NaN` is a JavaScript reserved word indicating that a number is not a legal number.
* Infinity (or -Infinity) is the value JavaScript will return if you calculate a number outside the largest possible number.
* Use +num or Number(num) to transform a string to a number.
* JavaScripts comparison operators are `===`, `!==`, `<`, `>`, `<=`, `>=`

## Data Types and Conditionals
JavaScript has the following data types: `number`, `bigint`, `string`, `boolean`, `null`, `undefined`, `symbol`, and `object`. The `object` type is the only non-primitive type.

`null` is a special value that represents "nothing" or "empty".

`undefined` represents an unassigned value.

### Strings
A string is a piece of text.

In JavaScript, you can choose single quotes `'`, double quotes `"`, or backticks ` to wrap your strings in.

Templates allow embedding of variables/expressions in a sing and respect line breaks. A template is defined using backticks.

#### String Methods
JavaScript strings are primitive and immutable. All string methods produce a new string without altering the original string.

The basic string methods are as follows: 
* `length`
* `slice(start, end)` - extracts part of a string and returns extracted parts
* `substring(start, end)` - same as `slice` but start and end values less than zero are treated as zero.
* `substr(start, length)`
* `replace()` - replaces specified value with new value
* `replaceAll()`
* `toUpperCase()`
* `toLowerCase()`
* `trim()`, `trimStart()`, and `trimEnd()`
* `padStart()` and `padEnd()`
* `chartAt()`, `[]`
* `split(separator)` - converts string to array

### Conditionals

#### Comparisons
* Comparison operators return boolean value
* Strings are compared letter by letter in "dictionary" order
* When values of different types are compared they are converted to numbers (except when using `===`).
* `null === undefined` but do not equal any other value

#### Conditional Statements
* `if`, `else`, `else if`, `switch`

#### Logical Operators
* `!!` (OR) - finds first truthy value
* `&&` (AND) - finds first falsy value
* `!` (NOT)
* "falsy" values - `0`, `""`, `null`, `undefined`, `NaN`
* "truthy" values - all other values


## JavaScript Developer Tools
## Function Basics
## Problem Solving
## Understanding Errors
## Clean Code
## Arrays and Loops
## DOM Manipulation and Events
## Object Basics