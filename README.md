# React useEffect setTimeout Memory Leak

This repository demonstrates a common error in React applications involving the `useEffect` hook and `setTimeout` that leads to memory leaks. The problem arises when a `setTimeout` function is used within `useEffect` without a cleanup function to cancel the timeout when the component unmounts.

## Bug Description
The `MyComponent` uses `useEffect` to increment a counter every second using `setTimeout`. However, it fails to include a cleanup function to cancel the timeout when the component is unmounted. This causes the counter to continue incrementing even after the component is no longer displayed, leading to memory leaks and unexpected behavior.

## Solution
The solution involves adding a cleanup function to the `useEffect` hook. This function is responsible for canceling the timeout using `clearTimeout` before the component unmounts, preventing memory leaks.

## How to reproduce
1. Clone the repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the counter behavior. Note that the counter will continue to increment after navigating away from the component in the browser.
