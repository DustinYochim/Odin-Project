# React

## Introduction to React

Generally speaking, a JavaScript library is a collection of pre-written code that’s designed to make development easier. This code can be reused/reimplemented in our own codebases to achieve complex tasks.

React provides powerful primitives (built-in functions/modules) that allow us to build user interfaces of varying complexities. Throughout this course, we’ll learn all about the functionality React provides and learn to build cool applications.

### Library vs Framework

Frameworks and libraries are both code written by someone else that helps you perform some common tasks in a less verbose way.

A framework inverts the control of the program. It tells the developer what they need. A library doesn’t. The programmer calls the library where and when they need it.

The degree of freedom a library or framework gives the developer will dictate how “opinionated” it is.

When you use a library, you are in charge of the flow of the application. You are choosing when and where to call the library. When you use a framework, the framework is in charge of the flow. It provides some places for you to plug in your code, but it calls the code you plugged in as needed.

### Knowledge Check

- The purpose of react is to make building user-interfaces easier.
- Advantages of React
  - Composable - a function of combining parts or elements to form a whole.
  - Declarative - In react the DOM is declarative. We can make interactive UIs by changing the state of the component and React takes care of updating the DOM according to it.
  - Write once, and learn anywhere. - We can develop new features in React without re-writing the existing code.
  - Simple - The component-based approach, automatic rendering, and use of just plain JavaScript make React very simple to learn, build a web (and mobile applications), and support it.
  - SEO friendly - React affects the SEO by giving you a SPA (Single Page Application) which requires Javascript to show the content on the page which can then be rendered and indexed.
  - Fast, efficient, and easy to learn - It contains pre-built patterns and functions that can be chosen and combined like building blocks to create fast, appealing, and scalable projects in less time as compared to designing the entire application line by line.
  - Guarantees stable code - ReactJS solely use downward data flow to ensure that even minor changes in the child structures won’t have an impact on their parents.

## Setting Up A React Environment

Creating a react app from scratch is hard as it would involve configuring at least package management, module bundling, compilation, and react itself. Toolchains such as vite, gatsby, and NextJS help us by setting it all up for us.

### Creating a React App

`npm create vite@latest my-first-react-app -- --template react`

### Knowledge Check

- What are some of the ways we can start a new React project?
  - using Vite, Gatsby, or NextJS
- Why should we initially be using pre-made toolchains instead of making our own?
  - It is hard to create a React app from scratch.
- What is Vite and why would we use it?
  - Vite is a toolchain that can be used to setup a React app and automatically configures package management, module bundling, compilation, and React itself.
- What command can we run to scaffold a new React project using Vite?
  - `npm create vite@latest`
- What is in the public folder?
  - static files such as images, icons, and project information
- What is in the src folder?
  - the source code of your project
- Why are the React Developer Tools useful?
  - They help you debug your React application to verify components are receiving the correct props and holding hte correct state and can help identify performance issues.

## React Components

React lets you break a UI down into independent reusable chunks. For example, a website could be broken down into the following components:

- `App`, which represents the main application and will be the parent of all other components.
- `Navbar`, which will be the navigation bar.
- `MainArticle`, which will be the component that renders your main content.
- `NewsletterForm`, which is a form that lets a user input their email to receive the weekly newsletter.

These reusable chunks can be thought of as JavaScript functions that take some input and return a React element.

### How to Create Components

React components are essentially JavaScript functions that return JSX.

```js
// Greeting.jsx
function Greeting() {
  return <h1>Hello, World!</h1>;
}

export default Greeting;
```

React components must be capitalized or they will not function as expected.

This function lives in its own file, and because we want to be able to use it in other places in our code we use imports and exports to share it.

For example, our application starts in `main.jsx`.

```js
// main.jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";
import "./index.css";
import App from "./App.jsx"; // import the app so that we can render it in DOM

// Entry point of the application
createRoot(document.getElementById("root")).render(
  <StrictMode>
    <App />
  </StrictMode>
);
```

`main.jsx` imports the `App` function from `App.jsx` and renders it.

```js
// App.jsx
import MainArticle from "./MainArticle";
import { Navbar } from "./Navbar";
import { NewsletterForm } from "./NewsletterForm";

function App() {
  return (
    <>
      <Navbar />
      <MainArticle />
      <NewsletterForm />
    </>
  );
}

export default App;
```

Similarly, our `App.jsx` imports and inserts other React components.

### Knowledge Check

- What does a React element look like?
  - A React element looks like a JavaScript function that returns JSX.
- How would you create a functional component?
  - By creating a JavaScript function that returns JSX.
- How do you export and then import a component?
  - You export your JavaScript function that is returning JSX using either named or default exports, you then import it into the file you want to use it in.

## What is JSX?

JSX is a syntax extension for JavaScript that lets you write HTML-like markup inside a JavaScript file.

Essentially, JSX is syntactic sugar for the React createElement function. This function creates a React element, which is a plain object, so JSX compiles down to plain JavaScript objects.

When using JSX you must:

1. Return a single root element.
2. Close all tags.
3. camelCase **most** things.

You can reference dynamic values inside of JSX using `{}`. For example,

```js
export default function Avatar() {
  const avatar = "https://i.imgur.com/7vQD0fPs.jpg";
  const description = "Gregorio Y. Zara";
  return <img className="avatar" src={avatar} alt={description} />;
}
```

`{}` allows you to write JavaScript code inside of JSX.

### Knowledge Check

- What is JSX?
  - JSX is a syntax extension for JavaScript that helps you represent HTML.
- Why do we use JSX?
  - To create React elements.
- What are the three rules of JSX?
  - Return a single root element, close all tags, and camelCase most things.
- How do you reference a dynamic value inside of your JSX?
  - Using `{}`.

## Rendering Techniques

### Rendering a List of Elements in JSX

```js
function FavoriteAnimals() {
  let animals = ["Dog", "Cat", "Lion", "Monkey", "Dolphin"];

  return (
    <>
      <h3>My Favorite Animals</h3>
      <ul>
        {animals.map((animal) => {
          return <li key={animal}>{animal}</li>;
        })}
      </ul>
    </>
  );
}

export default FavoriteAnimals;
```

The `key` in the `<li>` elements is required for React to know the identity of each element in the list.

### Rendering a List of Components in JSX

`props` are arguments that are passed into components.

```js
function ListItem(props) {
  return <li>{props.animal}</li>;
}

function List(props) {
  return (
    <ul>
      {props.animals.map((animal) => {
        return <ListItem key={animal} animal={animal} />;
      })}
    </ul>
  );
}

function App() {
  const animals = ["Lion", "Cow", "Snake", "Lizard"];

  return (
    <div>
      <h1>Animals: </h1>
      <List animals={animals} />
    </div>
  );
}
```

### Conditionally Rendering UI

#### Using the Ternary Operator

```js
function List(props) {
  return (
    <ul>
      {props.animals.map((animal) => {
        return animal.startsWith("L") ? <li key={animal}>{animal}</li> : null;
      })}
    </ul>
  );
}

function App() {
  const animals = ["Lion", "Cow", "Snake", "Lizard"];

  return (
    <div>
      <h1>Animals: </h1>
      <List animals={animals} />
    </div>
  );
}
```

#### Using the `&&` Operator

```js
function List(props) {
  return (
    <ul>
      {props.animals.map((animal) => {
        return animal.startsWith("L") && <li key={animal}>{animal}</li>;
      })}
    </ul>
  );
}

function App() {
  const animals = ["Lion", "Cow", "Snake", "Lizard"];

  return (
    <div>
      <h1>Animals: </h1>
      <List animals={animals} />
    </div>
  );
}
```

When using && for conditional rendering, don’t put numbers on the left side.

#### Other Ways to Render Conditionally

You can also use `if`, `if/else`, and `switch` statements to conditonally render something.

```js
function List(props) {
  if (!props.animals) {
    return <div>Loading...</div>;
  }

  if (props.animals.length === 0) {
    return <div>There are no animals in the list!</div>;
  }

  return (
    <ul>
      {props.animals.map((animal) => {
        return <li key={animal}>{animal}</li>;
      })}
    </ul>
  );
}

function App() {
  const animals = [];

  return (
    <div>
      <h1>Animals: </h1>
      <List animals={animals} />
    </div>
  );
}
```

#### Knowledge Check

- How do you render a list of elements/components in JSX?
  - typically by calling the `.map()` function on the specific `prop`.
- What are the ways you could render UI conditionally?
  - ternary operator, `&&`, `if`, `if/else`, `switch` statements.
- How would you conditionally return JSX?
  - using the `filter()` method.
- Where to get the `key`?
  - Data from a database: If your data is coming from a database, you can use the database keys/IDs, which are unique by nature.
  - Locally generated data: If your data is generated and persisted locally (e.g. notes in a note-taking app), use an incrementing counter, `crypto.randomUUID()` or a package like `uuid` when creating items.

## Keys in React

### Why does React need keys?
When a list is updated for whatever reason (either from a server or a user interaction), React matches the keys of each of the previous list items to the updated list. If there were any changes, React will only update the items that have changed.

JSX elements directly inside a map() call always need keys!

As long as keys remain consistent and unique, React can handle the DOM effectively and efficiently.

### How do you use keys?
Keys are passed into the component or a DOM element as a prop.
```js
<Component key={keyValue} />
```

### Where should the key value come from?
Ideally, there should be some identifier that is unique to each item in the list. Most databases assign a unique id to each entry, so you shouldn’t have to worry about assigning an id yourself. If you are defining data yourself, it is good practice to assign a unique id to each item. You can use the crypto.randomUUID() function to generate a unique id.


```js
// a list of todos, each todo object has a task and an id
const todos = [
  { task: "mow the yard", id: crypto.randomUUID() },
  { task: "Work on Odin Projects", id: crypto.randomUUID() },
  { task: "feed the cat", id: crypto.randomUUID() },
];

function TodoList() {
  return (
    <ul>
      {todos.map((todo) => (
        // here we are using the already generated id as the key.
        <li key={todo.id}>{todo.task}</li>
      ))}
    </ul>
  );
}
```

The array index can be used as the key if the array is never going to change but it is still not recommended.


### Knowledge Check

- Why does React need keys?
- How do you use keys?
- Where should the key value ideally come from?
- When can we use an array index as the key value?
- What is an anti-pattern when using keys?


## Passing Data Between Components
