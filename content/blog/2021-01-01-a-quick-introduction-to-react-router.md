---
template: BlogPost
slug: /react-router
date: 2021-01-01T07:31:17.623Z
title: A Quick Introduction To React Router
tags:
  - javascript
  - react
  - router
thumbnail: /images/pexels-pixabay-416974.jpg
---
<!--StartFragment-->

**What is React Router?**

React Router is a routing library for React. The Router determines what should happen when a user chooses a certain path.

 Most web applications are Single-Page Applications(SPA) with components that are conditionally rendered. Router will decide which component to render based on the route specified in the URL.

To start using the router we have to install it using NPM.

> *npm install react-router-dom*

Once that is completed we have to import BrowserRouter, Route, and Switch from react-router-dom.

> *import { BrowserRouter as Router,Switch,Route } from 'react-router-dom'*

Next, let us look at how to render our components using React Router.

To work with the React Router we have to wrap all the components that are to be rendered inside the Router element.

The Route element specifies the component to be rendered  when the user visits a page with the given path.

```apex
function App() {
    return (
        <main>
            <Router>
              <Route path='/' component={Home} />
            </Router>
        </main>
    )
}
```

Now let us look at an example with multiple routes. This is where the relevance of Router comes in.

When we are rendering multiple components we have to add a Switch element to ensure that only one component is rendered at a time.

```apex
function App() {
    return (
        <main>
            <Router>
              <Switch>
				<Route path='/' component={Home} />
				<Route path=’/about’ component={About} />
                <Route path=’/contact’ component={Contact} />
              </Switch>
            </Router>
        </main>
    )
```

In the above example, you might have noticed that the path for the Home component is just a /. The path for other components also starts with a /. Route element will render the first component for which its path matches the URL. To avoid getting undesired results due to the above reason we have to add exact to the Route element.

```apex
function App() {
    return (
        <main>
            <Router>
              <Switch>
				<Route path='/' component={Home} exact />
				<Route path=’/about’ component={About} />
                <Route path=’/contact’ component={Contact} />
              </Switch>
            </Router>
        </main>
    )
```

To navigate to these components using clickable links we set up a new component Nav. To create links we need the Link element.

> *import {Link} from 'react-router-dom'*

Wrap the Link element around the clickable text. Give it an attribute of 'to' that specifies the path it leads to.

```apex
function Nav() {
  return (
    <div>
      <Link to="/">Home </Link>
      <Link to="/about">About </Link>
      <Link to="/contact">Contact </Link>
    </div>
  );
};
```

Hope you were able to get a basic understanding of React Router and enjoyed reading the article. Keep exploring!!

<!--EndFragment-->