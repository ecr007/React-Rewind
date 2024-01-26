# React Rewind

- Is a JavaScript Library
- To work with react is needed use React Developer Tool extension
- react.dev (Official Web)
- react.new (Online Editor and Sandbox)
- CDN: Content Delivery Network.

## Getting started with react

To create an element with **react@17** we use ReactDOM.render() function.

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

