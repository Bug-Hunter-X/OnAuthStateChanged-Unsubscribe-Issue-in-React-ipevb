# Firebase onAuthStateChanged Unsubscribe Issue

This repository demonstrates a common issue encountered when using Firebase's `onAuthStateChanged` within a React component: the listener not properly unsubscribing when the component unmounts. This can lead to memory leaks and unexpected behavior.

The `authBug.js` file showcases the problematic code.  The `authSolution.js` file provides a corrected implementation that ensures proper cleanup.

## Problem
The original code fails to correctly unsubscribe from the `onAuthStateChanged` listener when the component is unmounted. This results in the listener continuing to run even after the component is removed from the DOM.

## Solution
The solution uses a cleanup function within a `useEffect` hook to ensure that the unsubscribe function is called when the component unmounts, resolving the memory leak issue.