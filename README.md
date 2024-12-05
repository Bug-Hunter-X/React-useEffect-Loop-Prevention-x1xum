# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React's `useEffect` hook: an infinite loop caused by a missing dependency in the dependency array.

## Description
The `MyComponent` component uses `useEffect` to set up a timer that increments a counter every second. However, the dependency array is empty (`[]`), meaning the effect runs only once after the initial render, and never again.  This creates an infinite loop because the function updates `count`, which triggers a re-render, which triggers the effect again, and so on.

## Solution
The solution involves adding the `count` variable to the dependency array so that the effect reruns whenever `count` changes. This prevents the infinite loop by correctly updating the interval.