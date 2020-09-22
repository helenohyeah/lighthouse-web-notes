# Week 2 Day 2 Lecture
Instructor: Andy Lindsay

## Blocking
* blocking code means a section of code that stops future code from executing
```javascript
for (let i = 0; i <= 1000; i++) {
  console.log(i);
}
console.log("Done!");
```
* the numbers 1-1000 will log before the Done! is logged therefore the loop is blocking any future code from running

## Asynchronous Programming & setTimeout
* the default timer value (idleTimeout) is __1 ms__
  * applies if you use any non positive integer (0, 'apple', -23)
* when the setTimeout is called, a counter starts at the timer value and the timeout function runs when the timer reaches 0
* if there is a blocking code then javascript will only run the asynchronous code (expired timeouts) after the synchronous blocking code is finished
```javascript
setTimeout(() => {
  // asynchronous function
}, 100);
for (let i = 0; i < 1000; i++) {
  // synchronous function
}
```
* even though the timer expires after 100 ms it will not run because javascript must finish running the loop (blocking code)
  * therefore timers are not guaranteed

### How do we get data out of an asynchronous call?
* use a callback, invoke the callback in a setTimeout and pass it through the callback
  * __Note:__ not all callbacks are asynchronous (e.g. map, filter, forEach are synchronous)

## setInterval
* it sets a new timer. When the timer ends, it sets a new timer using the same timeout
* __Note__: setTimeouts are rarely used in practice. setInterval are much more commonly used way to set a timeout

## File System Functions ('fs')
* A module that's part of a library within
* [Documentation for Node.js File System operations](https://nodejs.org/api/fs.html)

To import the modules into a .js file:
```javascript
// GOOD...
const fs = require('fs'); // looks for a package
// BAD...
const fs = require('./fs') // looks in that relative path for that file
```

To read the contents of an index.html file using sychronous control flow
```javascript
const fileData = fs.readFileSync('./index.html', { encoding: 'utf-8' });
console.log(fileData);
```
* if the encoding isn't there, it will log the contents in hexadecimal buffer
* no error handler so it stops the node process

To read the contents of an index.html using asychronous control flow
```javascript
const fileData = fs.readFile('./index.html', { encoding: 'utf-8' }, (error, data) => {
  if (error) { // if no error, error is falsy usually null
    console.log(error);
  } else {
    console.log(data);
  }
}
```
* Node.js uses what's called error first callback because the error is first
* because it has an error handler we can choose what to do with an error (e.g. read a file that doesn't exist)
