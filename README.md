# React useEffect setInterval Memory Leak

This repository demonstrates a common error in React applications involving the `useEffect` hook and `setInterval`.  Forgetting to clear an interval when a component unmounts can lead to memory leaks and unexpected behavior. The example showcases the incorrect and corrected implementation to avoid the issue.

## Bug Description
The primary issue is the lack of cleanup in the `useEffect` hook. The `setInterval` function is used to update a counter, but without a proper `clearInterval` call in the cleanup function, the interval continues running after the component is removed from the DOM, causing a memory leak.

## Solution
The solution involves adding a `return` statement within the `useEffect` hook. This `return` statement is responsible for calling `clearInterval` and stops the interval when the component unmounts.