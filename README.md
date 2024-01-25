# React Rewind

- Is a JavaScript Library
- To work with react is needed use React Developer Tool extension
- react.dev (Official Web)
- react.new (Online Editor and Sandbox)
- CDN: Content Delivery Network.

## Getting started with react

To create an element with **react@17** we use ReactDOM.render() function.

```html
    <div id="root"></div>
```

```js
const root = document.getElementById("root");
const title = React.createElement("h1", null, "Hello World");


ReactDOM.render(title, root);
```

- ReactDOM.render(reactNode, domRoot, callback?): Renders a piece of JSX (React Node) into a browser DOM node.

