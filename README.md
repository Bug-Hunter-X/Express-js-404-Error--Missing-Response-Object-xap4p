# Express.js 404 Error: Missing Response Object

This repository demonstrates a common error in Express.js route handlers: forgetting to send a response object when handling errors such as a 404 Not Found error.  The provided `bug.js` file showcases this error, and `bugSolution.js` demonstrates the correct implementation.

## Bug Description

The route handler `/users/:id` attempts to fetch a user from a database. If the user is not found, it intends to send a 404 error. However, it omits the `res.send()` or a similar response-sending method. This leads to a hanging request that never completes.

## Bug Solution

The solution file, `bugSolution.js`, corrects the issue by explicitly including `res.status(404).send('User not found');` to send an appropriate response.