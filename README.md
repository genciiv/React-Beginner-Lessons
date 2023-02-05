# ReactJS Tutorial for Beginners

## 1.What is React ?

React is an open source javascript library for building user interfaces.
React is a project created and maintained by Facebook.
React has more than a 100 thousand stars on GitHub and a huge community behind it.
React has become increasingly 
popular among developers and is also one of the most sought out skill-sets by companies right now.

React has a component based architecture. This lets you break down your application into small encapsulated parts which can then be composed to make more complex UI.
React is declarative.
React will make it painless for you to create complex UIs by abstracting away the difficult parts. 
React will handle efficiently updating and rendering just the right components in your application when your data changes. 
DOM updates which is one of the more expensive operations is handled gracefully in React.

## 2.Components

React components implement a render() method that takes input data and returns what to display. This example uses an XML-like syntax called JSX. Input data that is passed into the component can be accessed by render() via this.props.

JSX is optional and not required to use React. Try the Babel REPL to see the raw JavaScript code produced by the JSX compilation step.

### A Stateful Component
In addition to taking input data (accessed via this.props), a component can maintain internal state data (accessed via this.state). When a component’s state data changes, the rendered markup will be updated by re-invoking render().

### An Application
Using props and state, we can put together a small Todo application. This example uses state to track the current list of items as well as the text that the user has entered. Although event handlers appear to be rendered inline, they will be collected and implemented using event delegation.


## 3.Functional Component
A functional component is a type of React component that is defined as a JavaScript function and doesn't have its own state or lifecycle methods. It receives props as an argument and returns a React element. It is used to present static data and can be used for simple components that don't require state or lifecycle methods. Example:

Syntax :

function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

## 4.Class Component

A class component is a type of React component that is defined using a class in JavaScript. It extends the React.Component class and can have its own state and lifecycle methods. Class components are used to manage state and perform more complex logic, such as making API calls or handling interactions. Example:

Syntax :

class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}

## 5.JSX

JSX is a syntax extension for JavaScript that allows writing HTML-like code within your JavaScript code. It is used in React to define the structure of components and render UI elements. JSX makes it easier to write and understand the structure of a React component, as it allows you to write HTML-like code instead of using JavaScript functions to build the component. When the code is transpiled, it is transformed into JavaScript code that can be understood by the browser.

Syntax :

const element = <h1>Hello, World!</h1>;

## 6.Props

In React, props (short for "properties") are inputs to a component. They are passed down from a parent component to a child component and allow the child component to receive data and render dynamic content. The child component can access the values of the props using this.props. Props are read-only and cannot be changed within the child component, ensuring that the parent-child relationship remains unidirectional.

example

function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

ReactDOM.render(
  <Welcome name="John" />,
  document.getElementById('root')
);
