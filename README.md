# JasmineCheatSheet

# Jasmine Cheat Sheet

[Jasmine](https://jasmine.github.io/) is a popular behavior-driven development (BDD) testing framework for JavaScript. It's commonly used to write tests for JavaScript code to ensure its correctness.

#### <span style="color: #ff5733;">Key Terminology</span>

- <span style="color: #ff5733;">**Suite**</span>: A group of related test cases.
- <span style="color: #ff5733;">**Spec**</span>: A single test case or test scenario.
- <span style="color: #ff5733;">**Matcher**</span>: A function that checks if the actual value meets an expected condition.

#### <span style="color: #ff5733;">Basic Test Structure</span>

\`\`\`javascript
describe('Suite Name', () => {
  // Setup code (optional)
  
  it('Spec Name', () => {
    // Test code and expectations
  });
  
  // More specs (optional)
});
\`\`\`

#### <span style="color: #ff5733;">Matchers</span>

Matchers are functions used within test expectations to check if a condition is met.

- \`expect(value).toBe(expectedValue)\`: Checks if \`value\` is strictly equal to \`expectedValue\`.

\`\`\`javascript
expect(2 + 2).toBe(4);
\`\`\`

- \`expect(value).toEqual(expectedValue)\`: Checks if \`value\` is deep-equal to \`expectedValue\` (for objects and arrays).

\`\`\`javascript
expect([1, 2, 3]).toEqual([1, 2, 3]);
\`\`\`

- \`expect(value).toBeTruthy()\`: Checks if \`value\` is considered truthy (not \`false\`, \`null\`, \`undefined\`, \`0\`, or \`''\`).

\`\`\`javascript
expect(true).toBeTruthy();
\`\`\`

- \`expect(value).toBeFalsy()\`: Checks if \`value\` is considered falsy (\`false\`, \`null\`, \`undefined\`, \`0\`, or \`''\`).

\`\`\`javascript
expect(false).toBeFalsy();
\`\`\`

#### <span style="color: #ff5733;">Spies</span>

Spies are used to mock or spy on function calls.

- \`spyOn(object, 'method')\`: Creates a spy for the specified method of an object.

\`\`\`javascript
const obj = { doSomething: () => {} };
spyOn(obj, 'doSomething');
\`\`\`

- \`expect(spy).toHaveBeenCalled()\`: Checks if a spy has been called.

\`\`\`javascript
expect(obj.doSomething).toHaveBeenCalled();
\`\`\`

- \`expect(spy).toHaveBeenCalledWith(arg1, arg2, ...args)\`: Checks if a spy has been called with specific arguments.

\`\`\`javascript
expect(obj.doSomething).toHaveBeenCalledWith('arg1', 'arg2');
\`\`\`

#### <span style="color: #ff5733;">Async Testing</span>

Jasmine provides mechanisms for handling asynchronous code.

- \`it('Spec Name', (done) => { /* Async test code */ done(); });\`: Indicates an asynchronous test, and you must call \`done()\` to signal completion.

\`\`\`javascript
it('Async Spec', (done) => {
  setTimeout(() => {
    expect(true).toBe(true);
    done();
  }, 1000);
});
\`\`\`

#### <span style="color: #ff5733;">Custom Matchers</span>

You can create custom matchers to enhance readability.

- \`beforeEach(() => { jasmine.addMatchers({ customMatcher: () => ({ compare: () => {} }) }); });\`: Define a custom matcher.

\`\`\`javascript
beforeEach(() => {
  jasmine.addMatchers({
    toBeEven: () => ({
      compare: (actual) => ({
        pass: actual % 2 === 0,
        message: 'Expected value to be even.',
      }),
    }),
  });
});
\`\`\`

- \`expect(value).toBeEven()\`: Use the custom matcher in a test expectation.

\`\`\`javascript
expect(4).toBeEven();
\`\`\`

#### <span style="color: #ff5733;">Spying on Functions</span>

Spies can be used to spy on function calls.

- \`spyOn(object, 'method')\`: Create a spy for the specified method of an object.

\`\`\`javascript
const obj = { doSomething: () => {} };
spyOn(obj, 'doSomething');
\`\`\`

- \`expect(spy).toHaveBeenCalled()\`: Check if a spy has been called.

\`\`\`javascript
expect(obj.doSomething).toHaveBeenCalled();
\`\`\`

- \`expect(spy).toHaveBeenCalledWith(arg1, arg2, ...args)\`: Check if a spy has been called with specific arguments.

\`\`\`javascript
expect(obj.doSomething).toHaveBeenCalledWith('arg1', 'arg2');
\`\`\`

This cheat sheet provides a quick reference to common Jasmine functions and concepts to help you write effective JavaScript tests.
`;

console.log(markdownContent);
