# Unhandled Error in Asynchronous Express.js Route Handler

This repository demonstrates a subtle Node.js error: an unhandled error thrown within an asynchronous callback of an Express.js route handler. The error is not caught, causing the server to crash.

## The Bug
The `bug.js` file contains the problematic code.  The core issue is the lack of error handling within the `setTimeout` callback. If the `Math.random()` function generates a number less than 0.5, a simulated database error is thrown. This error isn't caught, resulting in the server process unexpectedly terminating.

## The Solution
The `bugSolution.js` file provides a corrected version. It addresses the issue by using a `try...catch` block to handle potential errors within the asynchronous callback. This prevents the server from crashing and allows for more graceful error handling.

This example highlights the importance of robust error handling, especially in asynchronous code, to ensure application stability and prevent unexpected failures.