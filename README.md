# React setInterval Memory Leak

This repository demonstrates a common memory leak in React components that use `setInterval` within the `useEffect` hook without proper cleanup.  The bug involves failing to return a cleanup function from the `useEffect` callback. This results in multiple intervals running concurrently, causing memory to be consumed without being released.  The solution shows how to correctly implement `setInterval` with a cleanup function to avoid this issue.

## Bug

The `bug.js` file contains the faulty component.  The `setInterval` function is called without a cleanup mechanism. This means that even after the component unmounts, the interval continues to run, leading to a memory leak.

## Solution

The `bugSolution.js` file demonstrates the correct usage of `setInterval` within the `useEffect` hook. By returning a cleanup function from the `useEffect` callback, the interval is cleared when the component is unmounted, preventing the memory leak.

## How to reproduce

1. Clone the repository.
2. Navigate to the project directory.
3. Run `npm install` to install dependencies.
4. Run `npm start` to start the development server.
5. Observe the counter incrementing in the browser.  Check the browser's developer tools to observe the effect on memory consumption.