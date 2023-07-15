---
title: Deep Javascript Foundations by Kyle Simpson [Types & Coercion]
date: '2023-07-13'
tags: ['Javascript', 'Kyle Simpson', 'Course', 'Frontend Masters']
draft: true
summary: Notes on primitive types, NaN, new, coercion, booleans, equality from Frontendmasters course on Javascript by Kyle Simpson
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

```

```
