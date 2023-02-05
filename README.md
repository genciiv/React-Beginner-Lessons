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

## 7.State

In React, state is an object that holds data and determines a component's behavior. Unlike props, state can be changed within the component and is used to keep track of and respond to user events and interactions. State is only available to class components, not functional components.

The state of a component can be updated using this.setState method. When the state changes, React re-renders the component and its children to update the UI. It's important to avoid direct manipulation of the state object and always use setState to make changes to the state.

example 

class Example extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0
    };
  }

  incrementCount = () => {
    this.setState({
      count: this.state.count + 1
    });
  };

  render() {
    return (
      <div>
        <p>You clicked {this.state.count} times</p>
        <button onClick={this.incrementCount}>Click me</button>
      </div>
    );
  }
}


## 8.setState

In React, setState is a method used to update the state of a component. It's called within a class component to change the state, causing the component to re-render and update its UI.

The setState method takes an object as an argument that represents the new state. The object can contain one or more properties to update, and it will merge with the current state. setState is asynchronous and might be batched for performance reasons, so the state updates might not happen immediately after the call.

It's important to avoid direct manipulation of the state object and always use setState to make changes to the state.

example

class Example extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0
    };
  }

  incrementCount = () => {
    this.setState({
      count: this.state.count + 1
    });
  };

  render() {
    return (
      <div>
        <p>You clicked {this.state.count} times</p>
        <button onClick={this.incrementCount}>Click me</button>
      </div>
    );
  }
}

## 9.Event Handler

An event handler in React is a function that is triggered in response to a specific event, such as a user clicking a button or a component being updated. In React, event handlers are used to handle user interactions and updates to the component's state.

Event handlers in React are passed as props to the component and are attached to elements using the on keyword followed by the event name, such as onClick. When the specified event occurs, the event handler function is executed.

exapmle

class Example extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0
    };
  }

  incrementCount = () => {
    this.setState({
      count: this.state.count + 1
    });
  };

  render() {
    return (
      <div>
        <p>You clicked {this.state.count} times</p>
        <button onClick={this.incrementCount}>Click me</button>
      </div>
    );
  }
}

In this example, the incrementCount method is an event handler that is executed when the button is clicked. The event handler updates the component's state and causes the component to re-render.


## 10.Binding Event Handler

In React, when you pass a method as a prop or attach it to an event, such as onClick, you need to bind the this keyword so that the method can access the component's state and props. If you don't bind the this keyword, the method will be executed in the global context, and the component's state and props will not be available.

To bind the this keyword, you can either use the constructor method or use arrow functions. The constructor method is used to bind the this keyword to the component instance, making its state and props available to all its methods.

Example using the constructor method:

class Example extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0
    };
    this.incrementCount = this.incrementCount.bind(this);
  }

  incrementCount() {
    this.setState({
      count: this.state.count + 1
    });
  }

  render() {
    return (
      <div>
        <p>You clicked {this.state.count} times</p>
        <button onClick={this.incrementCount}>Click me</button>
      </div>
    );
  }
}
 
Example using arrow functions:

class Example extends React.Component {
  state = {
    count: 0
  };

  incrementCount = () => {
    this.setState({
      count: this.state.count + 1
    });
  };

  render() {
    return (
      <div>
        <p>You clicked {this.state.count} times</p>
        <button onClick={this.incrementCount}>Click me</button>
      </div>
    );
  }
}

In both examples, the incrementCount method is bound to the component instance, making the component's state and props available within the method. This allows the method to update the state and re-render the component when the button is clicked.


