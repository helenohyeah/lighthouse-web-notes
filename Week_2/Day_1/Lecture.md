# Week 2 Day 1 Lecture
Instructor: Jeremy Holman

## Manual vs. Automated Testing
* __Manual:__
  * cheapter to start
  * allows human intelligence/creativity
* __Automated:__
  * cheaper in the "long run" (> 5 mins)
  * reliable, consistent, and predictable
  * faster turnaround
  * cheaper to handle large volume of tests
  * can test things only a machine can measure
  * doubles as documentation

## Notes
* Want to bundle multiple functions together for export? Bundle them into an Object
```javascript
// in the export file
module.exports = {
  foo: foo, // foo function
  bar: bar // bar function
}

// in the file where you're using the exported functions
const reqs = require('./example');
const foo = reqs.foo;
const bar = reqs.bar;
```
## Mocha and Chai
* __Chai:__
  * Assertion library that can be used as part of your testing framework
  * [Assertion Documentation](https://www.chaijs.com/api/assert/)
* __Mocha:__
  * Test runner that makes asynchronous testing simple (discovers, runs, displays tests)
  * [Documentation](https://mochajs.org/)