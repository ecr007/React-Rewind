# React Components

Components are JavaScript functions that returns JSX code.

Note: Create components or function with capital letter. (Header or BodyList) 

```js

    const Header = (params) => {
        return (<h1>{params.title}</h1>);
    }

    const Body = () => {
        return (
            <div>
                <p>Content</p>
            </div>
        );
    }

    const App = () => {
        return (
            <div>
                <Header title="Hello World"/>
                <Body />
            </div>
        );
    }

    ReactDOM.render(<App />, root);
```

## Adding Component Properties

The each component receive a object as a parameter.

```js

const Footer = (params) => {
    return (
        <div>
            <p>Copyright {params.name} All right Reserved.</p>
        </div>
    )
}

const App = () => {
    return (
        <Header />
        <Body />
        <Footer year={new Date().getFullYear()}>
    )
}
```

## Working with lists

React sometimes return a warning: about unique key prop, to solve it only pass the key="" parameter with an unique value.

```jsx
const names = ["Juan","Rosa", "Bolivar"];

const List = function(params){
    return (
        <ul>
            params.names.map((item, i) => {
                return (<li key={i}>{item}</li>);
            });
        </ul>
    );
}

ReactDOM.render(<List names={names}>);
```

## Displaying Images with React

is equal to HTML

```js
const Logo = () => {
    return (
        <img src="logo.png" alt="Help for Screen Readers">
    );
}
```

## Using fragments
Are something to keep in mind is that instead of using a div you can use what's called a React Fragment 

```js
const App = () => {
    return (
        <React.Fragment>
            ....
        </React.Fragment>
    )

    // It's also possible to use an even shorter syntax for this. 
    // But we have to make sure that we're using a specifict versions of React

    return (
        <>
            ...
        </>
    )
}
```