# Express.js Route Handler Missing Error Handling

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input.  The provided code attempts to access a user based on an ID parameter, but lacks proper validation and error handling for non-numeric or missing IDs.

## Bug

The `bug.js` file contains the problematic code.  It uses `parseInt` to convert the ID to a number but doesn't handle potential errors such as `NaN` (Not a Number) that would result from a non-numeric input. This leads to unexpected crashes or incorrect behavior.

## Solution

The `bugSolution.js` file shows the corrected code.  It includes comprehensive error handling:

*   It checks if the `userId` is a number using `isNaN`.
*   It returns a 400 Bad Request error if the ID is invalid.
*   It handles the case where the user is not found with a 404 Not Found error.

This improved handling prevents unexpected crashes and returns appropriate HTTP status codes to the client.