# Firebase onAuthStateChanged Unsubscribe Issue

This repository demonstrates a common issue encountered when using Firebase's `onAuthStateChanged` listener: failure to properly unsubscribe when the component unmounts. This can lead to memory leaks and unexpected behavior.

The `authBug.js` file showcases the problematic code, while `authBugSolution.js` provides the corrected implementation.  The solution ensures that the listener is detached when the component is no longer needed, preventing resource exhaustion.

## Reproducing the Bug

1. Clone this repository.
2. Install dependencies: `npm install firebase`
3. Run the application. Observe the console logs for authentication status changes.
4. Notice that even after navigating away from the component using the listener, the listener continues to log authentication events.

## Solution

The solution involves utilizing the `useEffect` hook in React (or equivalent in other frameworks) to properly unsubscribe from the listener during component unmount.  The corrected code is demonstrated in `authBugSolution.js`.