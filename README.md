# Node.js Server Hang Issue

This repository demonstrates a common issue in Node.js where long-running tasks in request handlers can block the event loop, making the server unresponsive. The `server.js` file shows the problem, while `serverSolution.js` presents a solution using asynchronous operations to prevent blocking.

## Problem

The `server.js` file creates a simple HTTP server.  However, the request handler includes a `while` loop that simulates a long-running task (5 seconds). During this time, the server is unresponsive to new requests.  This is because Node.js uses a single-threaded event loop, and long-running synchronous operations block this loop.

## Solution

The `serverSolution.js` file addresses this by using asynchronous operations (using `setTimeout`) to handle the long-running task. This allows the event loop to continue processing other requests even while the long-running task is executing.