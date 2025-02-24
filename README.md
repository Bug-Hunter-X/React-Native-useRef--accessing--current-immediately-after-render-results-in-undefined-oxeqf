# React Native useRef: Immediate Access to .current After Render

This repository demonstrates a common error when using the `useRef` hook in React Native: attempting to access `ref.current` immediately after a component renders.  The ref's value might not be populated yet, leading to unexpected behavior or crashes, especially when interacting with native modules.

## The Problem

The `useRef` hook provides a mutable object that persists across renders. However, the value assigned to `ref.current` isn't guaranteed to be available instantly after the component mounts.  Accessing `ref.current` too early can result in `undefined`, potentially causing errors, especially when trying to use the ref with native modules or complex components. 

## Solution

The solution is to access `ref.current` only after the component has fully mounted and the ref is initialized. This can be achieved with the `useEffect` hook, ensuring the code runs after the initial render. 