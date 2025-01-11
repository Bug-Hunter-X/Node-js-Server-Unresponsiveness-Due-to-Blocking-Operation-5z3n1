# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js applications where a long-running synchronous operation in the request handler blocks the event loop, causing the server to become unresponsive. The `server.js` file contains the buggy code, while `serverSolution.js` provides a corrected version using asynchronous operations.

## Problem

The original `server.js` uses a `while` loop to simulate a 5-second operation. This synchronous loop blocks the event loop, preventing Node.js from handling other incoming requests during that time.  Any requests arriving during this period will be queued but won't be processed, leading to unresponsiveness.

## Solution

The `serverSolution.js` file demonstrates how to solve this by utilizing asynchronous operations. Asynchronous programming allows the event loop to remain responsive even when long-running tasks are being executed.