# React Router

Create React App does not inclide page routing.

React Router is the most popular solution.

## Add React Router
To add react router in your application, run this in the terminal from the root directory in the application. 

```sh
npm install react-router-dom@6

# Latest version 
npm install react-router-dom@latest
```

Source: https://github.com/remix-run/react-router

## Folder Structure 

To create an application with multiple page routes, let's first start with the file structure.

Within the ```src``` folder. We'll created a folder named ```pages``` with several files: 

- Layout.js
- Home.js
- Blog.js
- Error.js

## Basic Usage

Now we will use our Router in our index.js file. 

```js
import ReactDOM from 'react-dom/client';
import { BrowserRouter, Routes, Route} from 'react-router-dom';
import Layout from './pages/Layout.js';
import Home from './pages/Home.js';
import Blog from './pages/Blog.js';
import Error from './pages/Error.js';

export default 

```