# React setInterval Memory Leak

This repository demonstrates a common mistake when using `setInterval` within a React component's `useEffect` hook: forgetting to include a cleanup function to stop the interval when the component unmounts. This leads to a memory leak and unexpected behavior.

## Bug Description
The `MyComponent` component uses `setInterval` to update the count every second. However, the interval is never cleared, resulting in the interval continuing to run even after the component is unmounted. This causes a memory leak as the component's state continues to be updated even though it's no longer rendered.

## Solution
The solution is to add a cleanup function to the `useEffect` hook. The cleanup function is responsible for clearing the interval when the component unmounts, preventing the memory leak.

## How to reproduce
Clone the repository and run `npm start`.

## How to fix
Refer to the `bugSolution.js` file for a corrected implementation.