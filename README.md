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

// Create React
const title = React.createElement("h1", reactOptions, "Hello Everyone");

ReactDOM.render(title, root);
```

- ReactDOM.render(reactNode, domRoot, callback?): Renders a piece of JSX (React Node) into a browser DOM node.

