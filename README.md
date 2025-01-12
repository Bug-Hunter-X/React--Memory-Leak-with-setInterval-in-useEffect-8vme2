# React: Memory Leak with setInterval in useEffect

This repository demonstrates a common mistake in React applications: using `setInterval` within `useEffect` without providing a cleanup function.  This leads to a memory leak because the interval continues indefinitely, even after the component unmounts.

## Bug Description
The `MyComponent` function uses `setInterval` to increment a counter every second. However, it fails to clear the interval when the component unmounts, resulting in a memory leak.

## Solution
The solution involves using the return value of `useEffect` to clear the interval.  This ensures that the interval is stopped when the component is no longer needed.