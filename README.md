# React useEffect Dependency Array Error: Stale Closures

This repository demonstrates a common error in React's `useEffect` hook: forgetting to include state variables in the dependency array.  This can lead to unexpected behavior, particularly stale closures, where the callback function uses outdated values.

The `bug.js` file shows the incorrect implementation, while `bugSolution.js` provides the corrected version.

## How to Reproduce

1. Clone the repository.
2. Run `npm install` to install dependencies (if any).
3. Run the application (method depends on your React setup).
4. Observe the console output and the unexpected behavior resulting from the incorrect dependency array.

## Solution

The core issue is that the `useEffect` callback in `bug.js` captures the `count` variable from the closure. Without listing `count` in the dependency array, the useEffect function always uses the value of `count` from the initial render, instead of reacting to changes.  The solution is to include `count` as a dependency.