# React Rewind

- Is a JavaScript Library
- To work with react is needed use React Developer Tool extension
- react.dev (Official Web)
- react.new (Online Editor and Sandbox)
- CDN: Content Delivery Network.

## Getting started with react

To create an element with **react@17** we use ReactDOM.render() function.

It Is necessary to load React Scripts
```html
<!-- index.html -->
<script crossorigin src="https://unpkg.com/react@17/umd/react.development.js" defer></script>
<script crossorigin src="https://unpkg.com/react-dom@17/umd/react-dom.development.js" defer></script>
<script src="app.js?v=1" defer></script>
```

```js
const body = document.querySelector("body");

const root = document.createElement("div");
root.setAttribute("id","root");

// Set root
body.append(root);

const reactOptions = {
    className: "title",
    style: {
        color: "#333",
        fontSize: "28px",
        backgroundColor: "#f2f2f2",
        padding: "32px",
        border: "3px dashed #333",
        fontFamily: "Helvetica",
        textAlign: "center",
        borderRadius: "6px",
        margin: "32px 60px"
    },
}

const paragraph = React.createElement("p", {}, "Hello World");

// Create React
const title = React.createElement("div", reactOptions, paragraph);

ReactDOM.render(title, root);
```

- React.createElement(type, props, ...children): lets you create a React Element. It serves as an alternative to writing JSX. 

## Refactoring Elements using JSX

**What is JSX?**
JavaScript as XML. It's a syntax extension for JavaScript Recommended by React for building user intefaces. JSX allows you to write HTML elements and components in a syntax that looks similar to XML or HTML within JavaScript code.  

Note: Using curly braces to put variables ```{varName}``` inside String.

## Incorporating Babel

Working with JSX is necesary load Babel in the HTML file and using type="text/babel" parameter.

```html
<script crossorigin src="https://unpkg.com/react@17/umd/react.development.js" defer></script>
<script crossorigin src="https://unpkg.com/react-dom@17/umd/react-dom.development.js" defer></script>

<script src="https://unpkg.com/@babel/standalone/babel.min.js" defer></script>

<!-- Load React JSX Here -->
<script type="text/babel" src="babel.js" defer></script>
```

**How to inject dynamic content like variable or methods value with Babel**
Use curly braces 

```js
const name = "John doe";

const paragraph = <p>{name}</p>
```
