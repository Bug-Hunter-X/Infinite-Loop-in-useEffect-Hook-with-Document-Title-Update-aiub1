# React useEffect Infinite Loop Bug

This repository demonstrates a common bug in React applications involving the `useEffect` hook and document title updates.  The provided code creates an infinite loop because the title update triggers a re-render, leading to another title update, and so on. This example shows the problem and then presents a clear solution.

## Bug Description

The `useEffect` hook, without proper dependency array management, is used to update the document title based on a state variable (`count`). This update inside `useEffect` triggers a re-render, changing the state and subsequently causing another title update, resulting in an infinite loop.

## Solution

The issue is solved by adding the `count` variable to the dependency array of the `useEffect` hook. This ensures that the effect only runs when the `count` variable changes. Without it, the effect runs on every render, triggering the infinite loop.