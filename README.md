# Unresponsive Node.js Server

This repository demonstrates a common issue in Node.js where a long-running synchronous operation in a request handler can cause the server to become unresponsive. The provided `server.js` file contains the problematic code, while `serverSolution.js` offers a solution using asynchronous operations.

## Problem

Node.js is single-threaded, meaning only one operation can run at a time.  When a long-running synchronous task (like the 5-second loop in `server.js`) is executed within the request handler, it blocks the event loop. This prevents the server from accepting and processing new requests until the task completes, leading to unresponsiveness.

## Solution

The solution is to refactor the code to use asynchronous operations.  This allows other operations to continue while the long-running task is being processed in the background.  `serverSolution.js` demonstrates a solution using `setTimeout` to simulate an asynchronous operation.