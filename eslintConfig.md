## Jest Compenents
```
                                    JEST                                       
          ___________________________|_____________________________                
         |           |          |        |          |              |
    Globals   Jest Objects    Expect  Jest Mock  Jest Cli   Jest Configure

```

#### &nbsp;&nbsp;&nbsp;&nbsp;|| &nbsp;&nbsp;[Globals](./globals.md) &nbsp;&nbsp; ||  &nbsp;&nbsp;[EslintConfig](./eslintConfig.md) &nbsp;&nbsp;|| &nbsp;&nbsp;[Expect](./matchers.md)&nbsp;&nbsp;||&nbsp;&nbsp;[Mocks](./mock.md)&nbsp;&nbsp;||&nbsp;&nbsp;[Jest Objects](./jestObjects.md)&nbsp;&nbsp;||&nbsp;&nbsp;[Jest Cli](./jestCli.md)&nbsp;&nbsp;||&nbsp;&nbsp;[Jest Configure](./jest.config.md) &nbsp;&nbsp;||

## We can add Own rules in .eslintrc.json file

```json
{
  "env": {
    "browser": true,
    "es2021": true
  },
  "extends": ["eslint:recommended"],
  "parserOptions": {
    "ecmaVersion": 12,
    "sourceType": "module"
  },
  "plugins": [],
  "rules": {},
  "overrides": [
    {
      "files": ["tests/**/*.test.js", "tests/**/*.spec.js"],
      "env": {
        "jest/globals": true
      },
      "extends": ["plugin:jest/recommended", "plugin:jest/style"],
      "plugins": ["jest"],
      "rules": {
        "jest/no-alias-methods": "warn",
        "jest/no-commented-out-tests": "warn",
        "jest/no-conditional-expect": "error",
        "jest/no-deprecated-functions": "error",
        "jest/no-disabled-tests": "warn",
        "jest/no-done-callback": "error",
        "jest/no-duplicate-hooks": "error",
        "jest/no-export": "error",
        "jest/no-focused-tests": "error",
        "jest/no-hooks": "off",
        "jest/no-identical-title": "error",
        "jest/no-if": "error",
        "jest/no-interpolation-in-snapshots": "error",
        "jest/no-jasmine-globals": "error",
        "jest/no-jest-import": "error",
        "jest/no-large-snapshots": ["warn", { "maxSize": 300 }],
        "jest/no-mocks-import": "error",
        "jest/no-standalone-expect": "error",
        "jest/no-test-prefixes": "error",
        "jest/no-test-return-statement": "error",
        "jest/prefer-called-with": "warn",
        "jest/prefer-expect-assertions": "off",
        "jest/prefer-hooks-on-top": "error",
        "jest/prefer-spy-on": "warn",
        "jest/prefer-strict-equal": "warn",
        "jest/prefer-to-be-null": "warn",
        "jest/prefer-to-be-undefined": "warn",
        "jest/prefer-to-contain": "warn",
        "jest/prefer-to-have-length": "warn",
        "jest/prefer-todo": "warn",
        "jest/require-to-throw-message": "off",
        "jest/require-top-level-describe": "error",
        "jest/valid-describe-callback": "error",
        "jest/valid-expect": "error",
        "jest/valid-expect-in-promise": "error",
        "jest/valid-title": "warn"
      }
    }
  ]
}
```

- `jest/no-alias-methods:` Warns against using deprecated alias methods.
- `jest/no-commented-out-tests:` Warns against having commented out tests in your test files.
- `jest/no-conditional-expect:` Prevents conditional execution of expect() statements.
- `jest/no-deprecated-functions:` Errors on usage of deprecated Jest functions.
- `jest/no-disabled-tests:` Warns against using xit or xdescribe to disable tests.
- `jest/no-done-callback:` Errors on using the done callback, encouraging modern async testing patterns.
- `jest/no-duplicate-hooks:` Errors on duplicate setup and teardown hooks.
- `jest/no-export:` Errors on exporting from test files.
- `jest/no-focused-tests:` Errors on using fit or fdescribe for focusing tests.
- `jest/no-hooks:` Disallows all types of setup and teardown hooks (off by default).
- `jest/no-identical-title:` Errors on tests and describe blocks with identical titles.
- `jest/no-if:` Errors on conditional logic inside tests.
- `jest/no-interpolation-in-snapshots:` Errors on interpolation in snapshot filenames.
- `jest/no-jasmine-globals:` Errors on usage of Jasmine globals (Jest's predecessor).
- `jest/no-jest-import:` Errors on importing Jest itself in test files.
- `jest/no-large-snapshots:` Warns against large snapshots (configurable size limit).
- `jest/no-mocks-import:` Errors on importing from **mocks** directories outside of Jest's automatic mocking.
- `jest/no-standalone-expect:` Errors on expect() calls outside of test or hook functions.
- `jest/no-test-prefixes:` Errors on using test prefixes in test names (e.g., testShould).
- `jest/no-test-return-statement:` Errors on returning a value from test functions.
- `jest/prefer-called-with:` Suggests using .toHaveBeenCalledWith() or .toHaveBeenLastCalledWith().
- `jest/prefer-expect-assertions:` Encourages explicit assertion counts with expect.assertions() or expect.hasAssertions() (off by default).
- `jest/prefer-hooks-on-top:` Errors if setup and teardown hooks are not at the top of their block.
- `jest/prefer-spy-on:` Suggests using jest.spyOn() for creating spies.
- `jest/prefer-strict-equal:` Suggests using toEqual() for deep equality over toBe() for reference equality.
- `jest/prefer-to-be-null:` Suggests using .toBeNull() for null checks.
- `jest/prefer-to-be-undefined:` Suggests using .toBeUndefined() for undefined checks.
- `jest/prefer-to-contain:` Suggests using .toContain() for checking if an array contains a particular item.
- `jest/prefer-to-have-length:` Suggests using .toHaveLength() to check array length.
- `jest/prefer-todo:` Suggests using test.todo for tests to be implemented later.
- `jest/require-to-throw-message:` Requires expect().toThrow() to include a message (off by default).
- `jest/require-top-level-describe:` Errors if tests are not wrapped in a describe block.
- `jest/valid-describe-callback:` Errors on invalid callbacks in describe blocks.
- `jest/valid-expect:` Errors on invalid expect() usage.
- `jest/valid-expect-in-promise:` Errors on improperly handling expect() in promises.
- `jest/valid-title:` Warns against invalid titles in describe, test, and it blocks.

* ## jest/no-alias-methods

```javascript
it.only("uses the preferred name for only", () => {});
```

- ## jest/no-commented-out-tests

```javascript
// it('is a commented out test', () => {});
```

- ## jest/no-conditional-expect

```javascript
it("does not use expect conditionally", () => {
  expect(true).toBe(true);
});
```

- ## jest/no-deprecated-functions

```javascript
beforeAll(() => {});
```

- ## jest/no-disabled-tests

```javascript
// it.skip('is a disabled test', () => {});
```

- ## jest/no-done-callback

```javascript
it("does not use done callback", async () => {
  await Promise.resolve();
});
```

- ## jest/no-duplicate-hooks

```javascript
beforeEach(() => {});
it("avoids duplicate hooks", () => {});
```

- ## jest/no-export

```javascript
export const myTest = () => it("does not export tests", () => {});
```

- ## jest/no-focused-tests

```javascript
it("is not focused with fit", () => {});
```

- ## jest/no-hooks

```javascript
// Note: jest/no-hooks is set to "off", so no example needed.
```

- ## jest/no-identical-title

```javascript
it("has a unique title", () => {});
it("also has a unique title", () => {});
```

- ## jest/no-if

```javascript
// Note: Avoid using conditional logic inside tests.
```

- ## jest/no-interpolation-in-snapshots

```javascript
it("does not interpolate in snapshots", () => {
  expect("snapshot").toMatchSnapshot();
});
```

- ## jest/no-jasmine-globals

```javascript
// Note: Avoid using Jasmine globals like `spyOn`.
```

- ## jest/no-jest-import

```javascript
// Note: Avoid importing jest, use globals.
```

- ## jest/no-large-snapshots

```javascript
it("has a reasonably sized snapshot", () => {
  expect("<div></div>").toMatchSnapshot();
});
```

- ## jest/no-mocks-import

```javascript
// Note: Avoid importing from __mocks__ directly.
```

- ## jest/no-standalone-expect

```javascript
it("contains expect within a test block", () => {
  expect(true).toBe(true);
});
```

- ## jest/no-test-prefixes

```javascript
it("does not start with should", () => {});
```

- ## jest/no-test-return-statement

```javascript
it("does not return a value", () => {});
```

- ## jest/prefer-called-with

```javascript
it("uses toHaveBeenCalledWith", () => {
  const mockFn = jest.fn();
  mockFn("arg");
  expect(mockFn).toHaveBeenCalledWith("arg");
});
```

- ## jest/prefer-expect-assertions

```javascript
// Note: jest/prefer-expect-assertions is set to "off".
```

- ## jest/prefer-hooks-on-top

```javascript
beforeEach(() => {});
it("places hooks at the top", () => {});
```

- ## jest/prefer-spy-on

```javascript
it("uses jest.spyOn", () => {
  const obj = { method: () => {} };
  const spy = jest.spyOn(obj, "method");
  obj.method();
  expect(spy).toHaveBeenCalled();
});
```

- ## jest/prefer-strict-equal

```javascript
it("uses toStrictEqual for deep equality", () => {
  expect({ a: 1 }).toStrictEqual({ a: 1 });
});
```

- ## jest/prefer-to-be-null

```javascript
it("uses toBeNull for null checks", () => {
  expect(null).toBeNull();
});
```

- ## jest/prefer-to-be-undefined

```javascript
it("uses toBeUndefined for undefined checks", () => {
  expect(undefined).toBeUndefined();
});
```

- ## jest/prefer-to-contain

```javascript
it("uses toContain for array checks", () => {
  expect(["a", "b"]).toContain("a");
});
```

- ## jest/prefer-to-have-lengthl

```javascript
it("uses toHaveLength to check array length", () => {
  expect(["a", "b"]).toHaveLength(2);
});
```

- ## jest/prefer-todo

```javascript
test.todo("will be implemented later");
```

- ## jest/require-to-throw-message

```javascript
// Note: jest/require-to-throw-message is set to "off".
```

- ## jest/require-top-level-describe

```javascript
describe("contains all tests", () => {
  it("is a test within a describe block", () => {});
});
```

- ## jest/valid-describe-callback

```javascript
describe("valid describe callback", () => {
  it("is a valid test", () => {});
});
```

- ## jest/valid-expect

```javascript
it("uses expect correctly", () => {
  expect(true).toBe(true);
});
```

- ## jest/valid-expect-in-promise

```javascript
it("uses expect in a promise correctly", async () => {
  await expect(Promise.resolve(true)).resolves.toBe(true);
});
```

- ## jest/valid-title

```javascript
it("has a valid title", () => {});
```
