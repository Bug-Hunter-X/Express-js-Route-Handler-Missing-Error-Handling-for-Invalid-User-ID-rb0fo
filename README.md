# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input. Specifically, the `/users/:id` route fails to handle cases where the `id` parameter is not a valid integer.

## Bug Description
The provided code attempts to find a user based on the ID parameter.  However, it directly parses the parameter as an integer without any checks. If the ID is not a valid integer (e.g., a string, or a non-numeric string), `parseInt(userId)` will return `NaN`, and the `.find()` method will likely not find the user, but without a proper error handler, the server will silently fail or throw an error.