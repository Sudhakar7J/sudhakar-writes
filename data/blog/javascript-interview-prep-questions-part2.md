---
title: Javascript Interview Prep Questions (Part-2)
date: '2023-07-06'
tags: ['Javascript', 'Interview', 'Learning']
draft: false
summary: A blog on arrays, prop drilling, callback hell, new keyword and arrow functions.
images: []
layout: PostLayout
canonicalUrl:
---

### Javascript Basic Questions (Part-2)

## 1. How do you find if a given object is an array in JS?

- We can find if a given object is an array by .isArray(). If it returns true it is an array and vice versa.
- Visually, if an object is enclosed within [], it tends to be an empty array.

```javascript
function checkObject(arr) {
  // check if arr is array
  const result = Array.isArray(arr)

  if (result) {
    console.log(`[${arr}] is an array.`)
  } else {
    console.log(`${arr} is not an array.`)
  }
}

const array = [1, 2, 3]

// call the function
checkObject(array)
```

```javascript
Output
[1,2,3] is an array.
```

## 2. What is **Prop drilling** and how to avoid it?

- Passing of data from one component through several connected components to the component that needs the data.
- Can be avoided by using React Context `(useContext)`, just wrap it in `fn.provider` . It provides a way to pass data through multiple nested levels of components without having to manually pass that data to each level.

#### useContext()

- `useContext` is a React Hook that lets you read and subscribe to context from your component.

```javascript
const value = useContext(SomeContext)
```

## 3. What is Callback hell?

- When we nest multiple callbacks within a function is called a callback hell.
- It makes the code very difficult to understand and maintain.

## 4. What are arrow functions?

- Arrow functions are lexically scoped.
- With arrow functions the `this` keyword always represents the object that defined the arrow function i.e gets `this.` from where it was saved.

```javascript
let x = (x, y) => x * y
```

## 5. What is `new` keyword?

- It creates and returns objects automatically (automates).
- Creates an instance of an object by calling the constructor method.
