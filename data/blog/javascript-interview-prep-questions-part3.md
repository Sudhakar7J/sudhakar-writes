---
title: Javascript Interview Prep Questions (Pt-3)
date: '2023-07-08'
tags: ['Javascript', 'Interview', 'Learning']
draft: false
summary: Notes on function currying, react lifecycle, state and props.
images: []
layout: PostLayout
canonicalUrl:
---

### Javascript Basic Questions (Part-3)

## 1.What is function currying?

- Currying in Javascript transforms a function with multiple arguments into a nested series of functions, each taking a single argument.
- Currying helps you avoid passing the same variable multiple times, and it helps you create a higher order function.
- Currying is a transformation of functions that translates a function from callable as f(a, b, c) into callable as f(a)(b)(c)

```javascript
function curry(f) {
  // curry(f) does the currying transform
  return function (a) {
    return function (b) {
      return f(a, b)
    }
  }
}
// usage
function sum(a, b) {
  return a + b
}
let curriedSum = curry(sum)

console.log(curriedSum(1)(2)) // 3
```

## 2. What is Unmounting and Mounting? (React Lifecycle)

- There are 4 stages in a react lifecycle.

| No  |   Lifecycle    |
| --- | :------------: |
| 1   | initialization |
| 2   |    mounting    |
| 3   |    updating    |
| 4   |   unmounting   |

#### initialization

- This is the phase in which the component is going to start its journey by setting up the state and the props. This is usually done inside the constructor method.

#### mounting

- Mounting is the phase in which our React component mounts on the DOM.
- There are 2 methods in mounting. They are `componentWillMount()` and `componentDidMount()`.

#### updating

- This is where component’s state changes and hence, re-rendering takes place.
- the data of the component (state & props) updates in response to user events like clicking, typing and so on. This results in the re-rendering of the component.
- There are 3 methods in updating. They are `shouldComponentUpdate()` , `componentWillUpdate()` and `ComponentDidUpdate()`.

#### unmounting

- The component gets unmounted from the DOM in this phase.
- It has only one method and it is `componentWillUnmount()`.

## 3. What are props?

- The props in React are the inputs to a component of React.
- The main purpose of props is to provide different component functionalities such as:

1. Passing custom data to the React component.
2. Using through this.props.reactProp inside render() method of the component
3. Triggering state changes.

## 4. What is a state?

- State of a component is an object that holds some information that may change over the lifetime of the component.
- The important point is whenever the state object changes, the component re-renders.
- It is always recommended to make our state as simple as possible and minimize the number of stateful components.

## 5. Difference between React state and props.

- In React, both **state** and **props** are plain JavaScript objects and used to manage the data of a component, but they are used in different ways and have different characteristics.
- **state** is managed by the component itself and can be updated using the `setState() `function. Unlike props, state can be modified by the component and is used to manage the internal state of the component.
- Changes in the state trigger a re-render of the component and its children.
- **props** (short for "properties") are passed to a component by its parent component and are read-only, meaning that they cannot be modified by the component itself.
- props can be used to configure the behavior of a component and to pass data between components.

| props                             | state                                      |
| --------------------------------- | ------------------------------------------ |
| Immutable                         | Owned by its component                     |
| Has better performance            | Locally scoped                             |
| Can be passed to child components | Writeable/Mutable                          |
|                                   | has setState() method to modify properties |
|                                   | Changes to state can be asynchronous       |
