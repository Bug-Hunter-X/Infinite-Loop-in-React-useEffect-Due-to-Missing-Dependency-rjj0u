# React useEffect Infinite Loop Bug

This repository demonstrates a common bug in React applications involving the `useEffect` hook.  The bug arises from an incorrectly specified dependency array, leading to an infinite loop that renders the component constantly.

## Bug Description
The `MyComponent` function uses `useEffect` to update a counter every second. However, the dependency array is empty (`[]`), meaning the effect runs only once after the initial render. Because `setCount` modifies state, causing a re-render, the component falls into an infinite re-render loop which can freeze the browser tab.

## How to Reproduce
Clone this repository and run `npm install` to install the dependencies. Then, run `npm start` to start the development server.  You'll observe the counter rapidly incrementing, potentially causing your browser to freeze.

## Solution
The solution involves correctly specifying the dependency array to include `count`. This ensures that the effect only runs when the `count` state variable changes (which is still every second, as before, preventing the infinite loop).
