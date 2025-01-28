# Express.js Route Handler Error Handling Bug

This repository demonstrates a common bug in Express.js route handlers: missing error handling for invalid input.  The example focuses on a route that fetches a user by ID.  If the provided ID is not a valid integer, the application may crash or return an unexpected response.

## Bug Description

The original code attempts to parse the user ID (provided as a route parameter) directly as an integer without checking for potential errors (NaN). This can lead to exceptions if the ID is not a valid number format.  The code also lacks a robust mechanism for handling the case where a user with the specified ID is not found. 

## Solution

The solution introduces comprehensive error handling to gracefully handle cases where the user ID is invalid or a user with that ID does not exist.  It uses `isNaN()` to check the ID format and provides appropriate HTTP status codes (400 for bad request and 404 for not found).