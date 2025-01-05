# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: the lack of proper error handling for invalid input parameters. Specifically, this example shows a route that fetches a user by ID but fails to handle cases where the provided ID is not a valid number.

## Bug Description

The `bug.js` file contains an Express.js route handler that fetches a user by ID.  The handler attempts to parse the ID from the request parameters as an integer and uses that to find the user in an array called `users`.  However, it fails to check if the ID is a valid number before attempting the parsing, which leads to errors if a non-numeric ID is provided.  This could result in the application crashing or returning unexpected responses.

## Solution

The `bugSolution.js` file shows the corrected version of the route handler, which includes error handling for invalid input. The improved handler first checks if the ID is a valid number using `isNaN`. If not a number, or if the user is not found, it returns a 404 error response.