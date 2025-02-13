# useEffect Runs on Every Render in React

This repository demonstrates a common error in React's `useEffect` hook: the effect running on every render even when a dependency array is provided.  The problem arises from a misunderstanding of how the dependency array controls the effect's execution.

## Problem

The provided `MyComponent` uses `useEffect` to log the current `count` to the console.  Even with the dependency array `[count]`, the effect still runs on every render.

## Solution

The solution involves correctly specifying the dependencies in the `useEffect` hook's dependency array.  If the effect should only run when the `count` changes, then the dependency array must accurately reflect this.

## How to reproduce

1. Clone this repo.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the console logs during component interaction.  You'll notice logs printed for each render, not just changes in state.

## How to fix

The solution provided in `bugSolution.js` demonstrates how to fix the bug.  By using the `count` state correctly in the dependency array, the effect triggers only when the `count` variable updates its value. 
