---
title: Getting Started with JS v2 by Kyle Simpson [Programming Primer]
date: '2023-07-11'
tags: ['Javascript', 'Kyle Simpson', 'Course', 'Frontend Masters']
draft: false
summary: Notes on functions, values, types and basic Programming Primer from Frontendmasters course on Javascript by Kyle Simpson
images: []
layout: PostLayout
canonicalUrl:
---

## [Getting Started with JavaScript, v2](https://frontendmasters.com/courses/getting-started-javascript-v2/) by Kyle Simpson

##### [Course Materials](https://static.frontendmasters.com/resources/2019-03-07-deep-javascript-v2/deep-js-foundations-v2.pdf)

#### [Programming Primer Notes](https://frontendmasters.com/courses/getting-started-javascript-v2/values/)

### Operations

- JavaScript operators are symbols that are used to perform operations on operands.

### Types

- `typeof` operator is used to return a string that represents the type of JavaScript for a given value.

```javascript
console.log(typeof 42)
// Expected output: "number"

console.log(typeof 'blubber')
// Expected output: "string"

console.log(typeof true)
// Expected output: "boolean"
```

### Variables

- A variable is a named reference to a `value` (Representation of some place in memory).

### Expresions and Statements

- Part of a statement is an expression.

### If & Else (Decisions)

```js
if (condition) statement1

// With an else clause
if (condition) statement1
else statement2
```

### Loops

- The statements for loops provided in JavaScript are:

1. for statement
1. do...while statement
1. while statement
1. labeled statement
1. break statement
1. continue statement
1. for...in statement
1. for...of statement

```js
for (initialization; condition; afterthought) statement

//

for (let step = 0; step < 5; step++) {
  // Runs 5 times, with values of step 0 through 4.
  console.log('Walking east one step')
}
```

### Functions

- `functions` are first-class objects, because they can be passed to other functions, returned from functions, and assigned to variables and properties.
- They can also have properties and methods just like any other object. - What distinguishes them from other objects is that functions can be called.

```js
function square(number) {
  return number * number
}
```

#### function expression

- The `function` keyword can be used to define a function inside an expression.
- The main difference between a function expression and a function declaration is the function name, which can be omitted in function expressions to create anonymous functions.

```js
const getRectArea = function (width, height) {
  return width * height
}

console.log(getRectArea(3, 4))
// Expected output: 12
```
