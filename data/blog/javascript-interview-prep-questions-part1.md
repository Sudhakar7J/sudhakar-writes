---
title: Javascript Interview Prep Questions (Part-1)
date: '2023-07-05'
tags: ['JavaScript', 'Interview', 'Learning']
draft: false
summary: Javascript's basic questionnaire on Promises, Closures and working under the hood.
images: []
layout: PostLayout
canonicalUrl:
---

### Javascript Basic Questions

1. What is **Closure** ?

- Closure is a collection of all the variables in scope at the time of creation of the function.
- It helps in maintaining state(memoization)

```javascript
// closure example

function calculate(x) {
  function multiply(y) {
    return x * y
  }
  return multiply
}

const multiply3 = calculate(3)
const multiply4 = calculate(4)

console.log(multiply3) // returns calculate function definition
console.log(multiply3()) // NaN

console.log(multiply3(6)) // 18
console.log(multiply4(2)) // 8
```

2. What is a **Promise** in JS?

- It is a two pronged function.
- Promises fn initiate web browser work and returns a placeholder object back in JS.
- It is just the placeholder for the data to expect when an api call is made.
- It has 4 states - pending, onfulfilled, onrejected, settled.

```javascript
//To Create a Promise
let promise = new Promise(function (resolve, reject) {
  //do something
})
```

- The `Promise()` constructor takes a function as an argument. The function also accepts two functions `resolve()` and `reject()`.

3. How does React work **under the hood**?

- At the core, react maintains a tree for the user that allows the user to do various computations.
- React maintains a virtual DOM and compares it with previous versions and updates it.
- ReactDOM recursively creates nodes depending on their ‘type’ property and appends them finally to the DOM. It receives two arguments, first is what to append and the second is what to append to.

4. Is Javascript a type language?

- Javascript is a loosely typed language as the variables can hold any type of data.
- The type of a variable, such as int, float, boolean, or String, must be declared in many other languages

5. What are **Higher-Order functions** in JS?

- A function that accepts other functions as arguments or returns other functions as their result.\
- `filter(), map(), reduce(), some()` are examples of Higher-Order Functions

```javascript
// Callback function, passed as a parameter in the higher order function
function callbackFunction() {
  console.log('I am  a callback function')
}

// higher order function
function higherOrderFunction(func) {
  console.log('I am higher order function')
  func()
}

higherOrderFunction(callbackFunction)
```
