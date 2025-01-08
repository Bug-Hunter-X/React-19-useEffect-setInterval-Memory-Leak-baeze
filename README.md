# React 19 useEffect setInterval Memory Leak
This repository demonstrates a common error in React 19 applications involving the `useEffect` hook and `setInterval`.  Specifically, it showcases a memory leak that occurs when the `setInterval` is not properly cleaned up.

## Bug Description
The `bug.js` file contains a `MyComponent` that uses `setInterval` within a `useEffect` hook to update a counter every second. The issue arises because the `setInterval` is never stopped. When the component unmounts, the interval continues running in the background, leading to a memory leak. 

## Solution
The `bugSolution.js` file provides a corrected version of `MyComponent`. The solution involves returning a cleanup function from the `useEffect` hook to stop the interval when the component is unmounted.