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

**Package and full documentation**
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
import ErrorPage from './pages/ErrorPage.js';

export default function AwesomeApp(){
    return (
        <BrowserRouter>
            <Routes>
                <Route path="/" element={<Layout />} >
                    <Route index element={<Home />} />
                    <Route path="/blog" element={<Blog />} />
                    <Route path="*" element={<ErrorPage />} />
                </Route>
            </Routes>
        </BrowserRouter>
    )
}

const main = ReactDOM.createRoot(document.getElementById("root"));
main.render(<AwesomeApp />);
```

## Example Explained 

We wrap our content first ```<BrowserRouter>...</BrowserRouter>```.

Then we difines our ```<Routes>```. An application can have multiples ```<Routes>```. Our basic example only use one.

```<Route>```s can be nested. The first <Route> has a path of ```/``` and renders the ```<Layout />``` component.

The nested ```<Route>```s inherit and add to the parent route. So the blog path is combined with the parent and becomes /blog.

The Home component route does not have a path but has an index attribute. That specifies this route as the default route for the parent route, which is ```/```.

Setting the path to * will act as a catch-all for any undefined URLs. This is great for a 404 error page or whatever error.

## Pages / Components

The Layout component has ```<Outlet>``` and ```<Link>``` elements.

The ```<Outlet>``` renders the current route selected.

```<Link>``` is used to set the URL and keep track of browsing history.

Anytime we link to an internal path, we will use ```<Link>``` instead of <a href="">.

The "layout route" is a shared component that inserts common content on all pages, such as a navigation menu.

## Components

```js
import { Outlet, Link } from "react-router-dom";

const Layout = () => {
  return (
    <>
      <nav>
        <ul>
          <li>
            <Link to="/">Home</Link>
          </li>
          <li>
            <Link to="/blog">Blog</Link>
          </li>
        </ul>
      </nav>

      <Outlet />
    </>
  )
};

export default Layout;

// Another File

const Home = () => {
  return <h1>Home</h1>;
};

export default Home;

// Another File
const Blog = () => {
  return <h1>Blog Articles</h1>;
};

export default Blog;

const errorPage = () => {
  return <h1>404</h1>;
};

export default errorPage;
```