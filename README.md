# Node.js Server Unresponsiveness

This repository demonstrates a common Node.js issue: server unresponsiveness caused by a long-running synchronous operation within the request handler.  The `bug.js` file contains the problematic code.  The solution is presented in `bugSolution.js`.

## Problem

The server uses a `while` loop to simulate a task that takes 5 seconds.  Because this is synchronous, Node.js's event loop is blocked, preventing it from handling subsequent requests. This results in the server appearing unresponsive or hanging.

## Solution

The solution involves using asynchronous operations or offloading the long-running task to a worker thread or a separate process.  `bugSolution.js` demonstrates a solution using asynchronous operations with `setTimeout` for demonstration purposes.  For production, explore worker threads or message queues for optimal performance.