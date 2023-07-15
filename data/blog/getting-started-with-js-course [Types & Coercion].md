---
title: Getting Started with JS, v2 by Kyle Simpson [Types & Coercion]
date: '2023-07-13'
tags: ['Javascript', 'Kyle Simpson', 'Course', 'Frontend Masters']
draft: false
summary: Notes on primitive types, NaN, new, coercion, booleans, equality, scope, closure, this, prototype and class from Frontendmasters course on Javascript by Kyle Simpson
images: []
layout: PostLayout
canonicalUrl:
---

## [Getting Started with JavaScript, v2](https://frontendmasters.com/courses/getting-started-javascript-v2/) by Kyle Simpson

##### [Course Materials](https://static.frontendmasters.com/resources/2019-03-07-deep-javascript-v2/deep-js-foundations-v2.pdf)

#### [Types & Coercion Notes](https://frontendmasters.com/courses/getting-started-javascript-v2/primitive-types/)

### Converting Types

- The way to convert from one type to another is `coercion`.

### Falsy and Truthy

1. Falsy

```js
- “”
- 0, -0
- null
- NaN
- false
- undefined
```

2. Truthy

```js
- “foo”
- 23
- { a:1 }
- [1,3]
- true
- function()
- ...
```

### Equality == vs ===

- == allows coercion (types different)

- === disallows coercion (types same)

### Scope

- Scope: where to look for things.

- **Undefined vs Undeclared** - Undefined is a variable that has been declared, but it doesn't have a value. A variable thats never been declared is undeclared.

### Immediately Invoked Function Expressions [IIFE]

- wrap the function with a function making it a function expression. and it's called as a value.

### Block Scoping

- This scope restricts the variable that is declared inside a specific block, from access by the outside of the block.

### Closure

- `Closure` is when a function remember the variables outside of it, even if you pass that function elsewhere.

### this

- this references the execution context for that call, determined by how the function was called.

```js
this.fn
```
