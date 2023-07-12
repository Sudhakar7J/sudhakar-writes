---
title: Redux and Redux Toolkit (RTK)
date: '2023-07-12'
tags: ['Redux', 'React', 'Course', 'Egghead']
draft: false
summary: Notes of Modern Redux and Redux Toolkit course on egghead.io
images: []
layout: PostLayout
canonicalUrl:
---

## [Modern Redux with Redux Toolkit (RTK) and TypeScript](https://egghead.io/lessons/react-intro-to-modern-redux-with-rtk-and-typescript) by Jamund Ferguson

## Redux

- `Redux` is a predictable state container for JavaScript apps.
- It is a single store containing "global" state.

## Dispatch

- The Redux store has a method called `dispatch`.
- The only way to update the state is to call `store.dispatch()` and pass in an action object.
- The store will run its reducer function and save the new state value inside, and we can call `getState()` to retrieve the updated value.

```javascript
store.dispatch({ type: 'counter/increment' })

console.log(store.getState())
// {value: 1}
```

## Reducer

- A `reducer` (also called a reducing function) is a function that accepts an accumulation and a value and returns a new accumulation. They are used to reduce a collection of values down to a single value.
- In Redux, the accumulated value is the `state object`, and the values being accumulated are `actions`. **Reducers calculate a new state given the previous state and an action**. They must be pure functions—functions that return the exact same output for given inputs.

## Why Use Redux?

- When an application grows bigger, it may have to share some state between components.
- This is where Redux comes into the picture. Being a state management library, Redux will basically store and manage all the application's states.

## What is a "thunk"?

- The word "thunk" is a programming term that means **_"a piece of code that does some delayed work"_**. Rather than execute some logic now, we can write a function body or code that can be used to perform the work later.

- For Redux specifically, "thunks" are a pattern of writing functions with logic inside that can interact with a Redux store's `dispatch` and `getState` methods.

```javascript
const thunkFunction = (dispatch, getState) => {
  // logic here that can dispatch actions or read state
}

store.dispatch(thunkFunction)
```

## What Makes Redux Predictable?

- State is **Read-only** in Redux. What makes Redux predictable is that to make a change in the state of the application, we need to dispatch an action which describes what changes we want to make in the state.

```javascript
//Empty Redux Store

import { configureStore } from '@reduxjs/toolkit'

export const store = configureStore({
  reducer: {},
})
```

```javascript
// Wrap the app in <Provider> so any component in app can access the redux store
import React from 'react'
import ReactDOM from 'react-dom'
import './index.css'
import App from './App'
import { store } from './app/store'
import { Provider } from 'react-redux'

ReactDOM.render(
  <Provider store={store}>
    <App />
  </Provider>,
  document.getElementById('root')
)
```

## Redux Workflow

![Redux](https://redux.js.org/assets/images/ReduxDataFlowDiagram-49fa8c3968371d9ef6f2a1486bd40a26.gif)

## Keeping data organized

- To keep data organized `slices` are used.
- A slice is the portion of Redux code that relates to a specific set of data and actions within the store‘s state.
- A slice reducer is the reducer responsible for handling actions and updating the data for a given slice, so each slice gets it's updated state.

`createslice()` takes an object with three main options fields:

- `name`: a string that will be used as the prefix for generated action types
- `initialState`: the initial state of the reducer
- `reducers`: an object where the keys are strings, and the values are "case reducer" functions that will handle specific actions

```javascript
const productSlice = createSlice({
  name: 'product',
  initialState,
  reducers: {},
})

//You can export this and import them into the store.ts file to use the specific slice as needed.
```

## Redux Hooks

- Redux provided `useSelector` and `useDispatch` hooks.

```javascript
import { TypedUseSelectorHook, useDispatch, useSelector } from 'react-redux'
import type { RootState, AppDispatch } from './store'

// Use throughout your app instead of plain `useDispatch` and `useSelector`
type DispatchFunc = () => AppDispatch
export const useAppDispatch: DispatchFunc = useDispatch
export const useAppSelector: TypedUseSelectorHook<RootState> = useSelector
```

## Selector function.

- A `selector function` is any function that accepts the Redux store state (or part of the state) as an argument, and returns data that is based on that state.
- A selector function can be used anywhere you have access to the entire Redux root state value.

```javascript
function TodoList() {
  // This anonymous arrow function is a selector!
  const todos = useSelector((state) => state.todos)
}
```
