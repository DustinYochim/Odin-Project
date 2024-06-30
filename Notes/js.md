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
* `&&` (AND) - finds first falsy values
* `!` (NOT)
* "falsy" values - `0`, `""`, `null`, `undefined`, `NaN`
* "truthy" values - all other values


## JavaScript Developer Tools

### Opening DevTools
There are three ways to open the Chrome DevTools menu:

1. From the Chrome Menu > More Tools > Developer Tools
2. Right-click anywhere on a webpage and select Inspect
3. Use the keyboard shortcut (Mac: `Opt` + `Cmd` + `C`)

### Basic Debugging
* In the console tab you can view and filter logs as well as evaluate expressions.
* In the sources tab you can view and debug js files, set breakpoints by clicking on line numbers, and step through code.
* The debugger tab has more advanced debugging features, such as control flow and viewing the call stack and variables.
* You can set different types of breakpoints such as line-of-code breakpoints, conditional breakpoints, and DOM breakpoints.

## Function Basics
A function is just a reusable block of code. There are functions that are built into the language and user-defined functions. If a function is part of an object, it is considered a **method**.

## Using Functions

### Defining a Function
```javascript
function myFunction() {
  alert("hello");
}
```
### Calling a Function
```javascript
myFunction();
```

### Function Parameters
Some functions require **parameters** to be specified when you are invoking them -- these are values that need to be included inside the function parentheses, which it needs to do its job properly. Parameters are sometimes called arguments, properties, or even attributes.

#### Default and Optional Parameters
If you're writing a function and want to support optional parameters, you can specify default values by adding = after the name of the parameter, followed by the default value:
```javascript
function hello(name = "Chris") {
  console.log(`Hello ${name}!`);
}

hello("Ari"); // Hello Ari!
hello(); // Hello Chris!
```

### Anonymous and Arrow Functions
An **anonymous function** is just a function that does not have a name. You'll often see anonymous functions when a function expects to receive another function as a parameter. In this case, the function parameter is often passed as an anonymous function.

```javascript
(function () {
  alert("hello");
});
```

This form of creating a function is also known as function expression. Unlike function declarations, function expressions are not hoisted.

When passing an anonymous function as a parameters there's an alternative form you can use, called an arrow function. Instead of `function(event)`, you write `(event) =>`:
```javascript
textBox.addEventListener("keydown", (event) => {
  console.log(`You pressed "${event.key}".`);
});
```

### Function Scope and Conflicts
When you create a function, the variables and other things defined inside the function are inside their own separate scope, meaning that they are locked away in their own separate compartments, unreachable from code outside the functions.

The top-level outside all your functions is called the global scope. Values defined in the global scope are accessible from everywhere in the code.

### Return Values
Return values are just what they sound like — the values that a function returns when it completes. 
## Problem Solving
From his book, “Think Like a Programmer”, V. Anton Spraul defines problem solving in programming as:

"Problem solving is writing an original program that performs a particular set of tasks and meets all stated constraints."

The three steps in the problem solving process are:
1. Understand the problem.
2. Plan
3. Divide and conquer

### Understand the problem

The first step to solving a problem is understanding exactly what the problem is.

To gain clarity and understanding of the problem, write it down on paper, reword it in plain English until it makes sense to you, and draw diagrams if that helps. When you can explain the problem to someone else in plain English, you understand it.

### Plan

Now that you know what you’re aiming to solve, don’t jump into coding just yet. It’s time to plan out how you’re going to solve it first. Some of the questions you should answer at this stage of the process:

* Does your program have a user interface? What will it look like? What functionality will the interface have? Sketch this out on paper.
* * What inputs will your program have? Will the user enter data or will you get input from somewhere else?
What’s the desired output?
* Given your inputs, what are the steps necessary to return the desired output?

The last question is where you will write out an algorithm to solve the problem. You can think of an algorithm as a recipe for solving a particular problem. It defines the steps that need to be taken by the computer to solve a problem in pseudocode.

####  Pseudocode

Pseudocode is writing out the logic for your program in natural language instead of code. It helps you slow down and think through the steps your program will have to go through to solve the problem.

### Divide and conquer

From your planning, you should have identified some sub-problems of the big problem you’re solving. Pick the smallest or simplest one and start there with coding.

It’s important to remember that you might not know all the steps that you might need up front, so your algorithm may be incomplete -— this is fine. Getting started with and solving one of the sub-problems you have identified in the planning stage often reveals the next subproblem you can work on. Or, if you already know the next subproblem, it’s often simpler with the first subproblem solved.

Many beginners try to solve the big problem in one go. Don’t do this. If the problem is sufficiently complex, you’ll get yourself tied in knots and make life a lot harder for yourself. Decomposing problems into smaller and easier to solve sub-problems is a much better approach. Decomposition is the main way to deal with complexity, making problems easier and more approachable to solve and understand.


## Understanding Errors
An error is a type of object built into the JS language, consisting of a name/type and a message. Errors contain crucial information that can assist you in locating the code responsible for the error, determining why you have this error, and resolving the error.

### Common Types of Errors
* Syntax error - when code you are trying to run is not written correctly. 
* Reference error - when you try to reference a variable that does not exist (within the current scope).
* Type error - an operand or argument passed to a function is incompatible with the type expected, attempting to modify a value that cannot be changed, attempting to use a value in an inappropriate way.
## Clean Code
Clean code is important because developers spend more time reading code than writing it.

### Naming Functions and Variables
* camelCase
* descriptive name
* consistent vocabulary
  * variables begin with noun or adjective, functions with a verb
* use searchable and immediately understandable names

### Indentation and Line Length
Generally, code will be easier to read if you manually break lines that are longer than about 80 characters. Many code editors have a line in the display to show when you have crossed this threshold. When manually breaking lines, you should try to break immediately after an operator or comma.

### Semicolons
Semicolons are mostly optional in JavaScript because the JS compiler will automatically insert them if they are omitted. This functionality CAN break in certain situations, leading to bugs in your code, so it is better to get used to adding semi-colons.


### Comments
The purpose of comments is not to provide pseudo code that duplicates your code. Good comments explain the reasons behind a piece of code.

### 10 Principles for Keeping Your Programming Code Clean
1. Revise your logic before coding.
2. Clearly expose the structure of the page.
3. Use correct indentation.
4. Write explanatory comments.
5. Avoid abusing comments.
6. Avoid extremely large functions.
7. Use naming standards for functions and variables.
8. Treat changes with caution
9. Avoid indiscriminate mixing of coding languages
10. Summarize your imports.


## Arrays and Loops
## DOM Manipulation and Events
## Object Basics