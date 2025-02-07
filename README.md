# JavaScript Closure Issue in Loops

This repository demonstrates a common JavaScript closure issue that often arises when using loops and asynchronous functions like `setTimeout`.

## The Bug

The `myFunction` attempts to log numbers 0-9 to the console with a 1-second delay between each number.  Due to the way closures work in JavaScript, all the callbacks created inside the `for` loop end up referencing the final value of `i` (which is 10), instead of the value of `i` at the time each callback was created.

## The Solution

The solution involves using an immediately invoked function expression (IIFE) to create a new scope for each iteration of the loop, effectively capturing the correct value of `i` in each callback.