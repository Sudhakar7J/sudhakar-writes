---
title: React Hooks - Part I
date: '2023-08-20'
tags: ['Javascript', 'React', 'Hooks']
draft: false
summary: Notes on React Hooks - useState, useEffect, useContext.
images: []
layout: PostLayout
canonicalUrl:
---

# Exploring the Power of React Hooks

React Hooks provide a cleaner and more concise way to work with state, lifecycle events, and more.

In this blog post, we'll delve into the world of React Hooks and provide code examples to illustrate their usage.

## What are React Hooks?

- React Hooks are functions that allow you to "hook into" React state and lifecycle features from functional components. Prior to Hooks, complex components required class components to handle state and side effects.
- Hooks were introduced in React 16.8 to address several issues related to code reuse, organization, and the steep learning curve associated with class components.

## 1. The useState Hook

`useState` is one of the most commonly used React Hooks. It enables you to add state to functional components. Here's how you can use it:

```jsx
import React, { useState } from 'react'

function Counter() {
  const [count, setCount] = useState(0)

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  )
}
```

In this example, the `useState` Hook is used to add a `count` state variable to the Counter component. The `setCount` function allows you to update the count state.

## 2. The useEffect Hook

`useEffect` is another essential React Hook used for handling side effects and lifecycle events within functional components

```jsx
import React, { useState, useEffect } from 'react'

function DataFetcher() {
  const [data, setData] = useState([])

  useEffect(() => {
    fetch('https://api.example.com/data')
      .then((response) => response.json())
      .then((data) => setData(data))
      .catch((error) => console.error('Error fetching data:', error))
  }, [])

  return (
    <div>
      <ul>
        {data.map((item) => (
          <li key={item.id}>{item.name}</li>
        ))}
      </ul>
    </div>
  )
}
```

In this snippet, the `useEffect` Hook is used to fetch data from an API and update the data state. The empty dependency array ([]) ensures that the effect runs only once after the initial render.

## 3. The useContext Hook

The `useContext` Hook facilitates the consumption of context values set by the Context API

```jsx
import React, { useContext } from 'react'

const ThemeContext = React.createContext()

function ThemedComponent() {
  const theme = useContext(ThemeContext)

  return <div style={{ background: theme.background, color: theme.text }}>Themed Content</div>
}
```

Here, the `useContext` Hook is used to access the theme object provided by the ThemeContext.
