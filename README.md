# Unhandled Promise Rejection in Express.js Route Handler

This repository demonstrates a common error in Express.js applications:  unhandled promise rejections in asynchronous route handlers.  When an asynchronous operation within a route handler throws an error, the application might crash silently without proper error handling. This example shows how to reproduce the issue and how to fix it.

## Bug
The `bug.js` file contains an Express.js application with a route handler that performs an asynchronous operation.  The operation can either resolve successfully or reject with an error.  However, the current error handling is insufficient—it only logs the error to the console but doesn't send an appropriate response to the client.

## Solution
The `bugSolution.js` file provides a corrected version of the application with proper error handling.  It uses a `try...catch` block to handle errors that might occur during the asynchronous operation and sends an appropriate error response to the client.  This prevents the application from crashing and provides a more robust user experience.

## How to Reproduce
1. Clone this repository.
2. Navigate to the directory.
3. Run `node bug.js`.  Refresh the page several times; you might see error messages in the console, but the application will likely remain operational.
4. Run `node bugSolution.js`. You'll see a proper error response from the server.