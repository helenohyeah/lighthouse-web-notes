# Day 2 Lecture
Instructor: Travis Borsa
Topic: Callbacks

## Notes
* functional expressions vs functional declaration
  * functional expressions aren't hoisted with a definition (technically the declaration is hoisted but the definition isn't hoisted)
  ```javascript
  const howdyAgain = function(param) {
    // function
  };
  ```
  * functional declarations are hoisted
  ```javascript
  function howdy(param) {
    // function
  };
  ```
* we can pass a function as a parameter
  * allows you to customize how a function runs (most of the function runs the same and one part of the logic can be swapped out)
  ```javascript
  const howdy = (param) => {
    console.log("howdy");
  }
  const howdyAgain = (param) => {
    console.log("howdyAgain");
  }
  const higherOrderHowdy = (howdyFunction) => {
    console.log("howdy starting in 3, 2, 1...");
    howdyFunction(); // part that can be swapped out by passing in different functions as a param
  }
  higherOrderHowdy(howdy);
  higherOrderHowdy(howdyAgain);
  ```
* the function received as a param is a "callback"
* to access a function in another file
```javascript
const eqArrays = require('./eqArrays.js');
```