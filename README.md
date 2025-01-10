# JavaScript Closure Issue in setTimeout Loop

This repository demonstrates a common issue encountered when using closures within `setTimeout` loops in JavaScript.  The problem stems from how variables are captured within the closure.  The seemingly straightforward `for` loop actually leads to unexpected behavior.

## The Bug

The provided `bug.js` file contains a function that uses a `for` loop to schedule multiple `setTimeout` calls.  The intention is to log the value of `i` at each iteration; however, due to closure behavior, all the `setTimeout` callbacks will log the final value of `i`, which is 10.

## The Solution

The `bugSolution.js` file offers a fix that utilizes an immediately invoked function expression (IIFE) to create a separate scope for each iteration of the loop, capturing the correct value of `i` within each closure.