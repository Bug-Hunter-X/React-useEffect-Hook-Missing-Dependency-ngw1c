# React useEffect Hook Missing Dependency

This repository demonstrates a common error in React's `useEffect` hook: omitting dependencies from the dependency array.  This leads to unexpected behavior and stale closures.

The `bug.js` file contains the buggy code. The `bugSolution.js` file provides the corrected version.

## Bug
The counter in `MyComponent` does not increment every second as expected due to the missing 'count' dependency in the `useEffect` hook's dependency array.  The `setInterval` callback will always use the initial value of `count` (0) because the closure doesn't update with the state change.

## Solution
Adding `count` to the dependency array ensures that the `useEffect` hook re-runs whenever the `count` state variable changes. The `setInterval` callback will then use the current `count` value.