## Jest Compenents
```
                                    JEST                                       
          ___________________________|_____________________________                
         |           |          |        |          |              |
    Globals   Jest Objects    Expect  Jest Mock  Jest Cli   Jest Configure

```

#### &nbsp;&nbsp;&nbsp;&nbsp;|| &nbsp;&nbsp;[Globals](./globals.md) &nbsp;&nbsp; ||  &nbsp;&nbsp;[EslintConfig](./eslintConfig.md) &nbsp;&nbsp;|| &nbsp;&nbsp;[Expect](./matchers.md)&nbsp;&nbsp;||&nbsp;&nbsp;[Mocks](./mock.md)&nbsp;&nbsp;||&nbsp;&nbsp;[Jest Objects](./jestObjects.md)&nbsp;&nbsp;||&nbsp;&nbsp;[Jest Cli](./jestCli.md)&nbsp;&nbsp;||&nbsp;&nbsp;[Jest Configure](./jest.config.md) &nbsp;&nbsp;||

# Globals   [For More Info Go](https://jestjs.io/docs/api)&#128072;

you don't have to require or import anything to use them. However, if you prefer explicit imports, you can do import {describe, expect, test} from '@jest/globals'.



* afterAll(fn, timeout)
* afterEach(fn, timeout)
* beforeAll(fn, timeout)
* beforeEach(fn, timeout)
* describe(name, fn)
* describe.each(table)(name, fn, timeout)
* describe.only(name, fn)
* describe.only.each(table)(name, fn)
* describe.skip(name, fn)
* describe.skip.each(table)(name, fn)
* test(name, fn, timeout)
* test.concurrent(name, fn, timeout)
* test.concurrent.each(table)(name, fn, timeout)
* test.concurrent.only.each(table)(name, fn)
* test.concurrent.skip.each(table)(name, fn)
* test.each(table)(name, fn, timeout)
* test.failing(name, fn, timeout)
* test.failing.each(name, fn, timeout)
* test.only.failing(name, fn, timeout)
* test.skip.failing(name, fn, timeout)
* test.only(name, fn, timeout)
* test.only.each(table)(name, fn)
* test.skip(name, fn)
* test.skip.each(table)(name, fn)
* test.todo(name)



These functions and methods are part of the Jest testing framework, which is widely used for testing JavaScript and React applications. Below, I'll explain each function and provide a simple example in JavaScript.

### `afterAll(fn, timeout)`
Runs a function after all tests in the current file have finished. The optional `timeout` parameter specifies the maximum time in milliseconds for the function to complete.

```javascript
afterAll(() => {
  console.log('All tests completed.');
});
```

### `afterEach(fn, timeout)`
Runs a function after each test in the current file. The optional `timeout` parameter specifies the maximum time in milliseconds for the function to complete.

```javascript
afterEach(() => {
  console.log('A test finished.');
});
```

### `beforeAll(fn, timeout)`
Runs a function before all tests in the current file. The optional `timeout` parameter specifies the maximum time in milliseconds for the function to complete.

```javascript
beforeAll(() => {
  console.log('Tests are starting.');
});
```

### `beforeEach(fn, timeout)`
Runs a function before each test in the current file. The optional `timeout` parameter specifies the maximum time in milliseconds for the function to complete.

```javascript
beforeEach(() => {
  console.log('A test is starting.');
});
```

### `describe(name, fn)`
Groups together several related tests. `name` is a string describing the group, and `fn` is a function containing the tests.

```javascript
describe('Math operations', () => {
  test('adds 1 + 2 to equal 3', () => {
    expect(1 + 2).toBe(3);
  });
});
```

### `describe.each(table)(name, fn, timeout)`
Runs the same suite of tests with different data sets. `table` is an array of arrays with the test data, and `name` is a string describing the group.

```javascript
describe.each([[1, 1, 2], [1, 2, 3], [2, 1, 3]])(
  'add(%i, %i)',
  (a, b, expected) => {
    test(`returns ${expected}`, () => {
      expect(a + b).toBe(expected);
    });
  }
);
```

### `describe.only(name, fn)`
Only runs the specified suite of tests, ignoring all other tests.

```javascript
describe.only('Only these tests run', () => {
  test('true is true', () => {
    expect(true).toBe(true);
  });
});
```

### `describe.only.each(table)(name, fn)`
Runs only the specified suite of tests with different data sets, ignoring all other tests.

```javascript
describe.only.each([[1, 1, 2], [1, 2, 3], [2, 1, 3]])(
  'add(%i, %i)',
  (a, b, expected) => {
    test(`returns ${expected}`, () => {
      expect(a + b).toBe(expected);
    });
  }
);
```

### `describe.skip(name, fn)`
Skips the specified suite of tests.

```javascript
describe.skip('These tests are skipped', () => {
  test('false is false', () => {
    expect(false).toBe(false);
  });
});
```

### `describe.skip.each(table)(name, fn)`
Skips the specified suite of tests with different data sets.

```javascript
describe.skip.each([[1, 1, 2], [1, 2, 3], [2, 1, 3]])(
  'add(%i, %i)',
  (a, b, expected) => {
    test(`returns ${expected}`, () => {
      expect(a + b).toBe(expected);
    });
  }
);
```

### `test(name, fn, timeout)`
Defines a single test. `name` is a string describing the test, and `fn` is the function containing the test code. The optional `timeout` parameter specifies the maximum time in milliseconds for the test to complete.

```javascript
test('2 + 2 equals 4', () => {
  expect(2 + 2).toBe(4);
});
```

### `test.concurrent(name, fn, timeout)`
Runs the test concurrently with other concurrent tests. Useful for running tests that don't interfere with each other.

```javascript
test.concurrent('Concurrent test 1', async () => {
  await new Promise(r => setTimeout(r, 1000));
  expect(true).toBe(true);
});

test.concurrent('Concurrent test 2', async () => {
  await new Promise(r => setTimeout(r, 1000));
  expect(true).toBe(true);
});
```

### `test.concurrent.each(table)(name, fn, timeout)`
Runs multiple concurrent tests with different data sets.

```javascript
test.concurrent.each([[1, 2, 3], [2, 3, 5], [3, 4, 7]])(
  'add(%i, %i)',
  async (a, b, expected) => {
    await new Promise(r => setTimeout(r, 1000));
    expect(a + b).toBe(expected);
  }
);
```

### `test.concurrent.only.each(table)(name, fn)`
Runs only the specified concurrent tests with different data sets.

```javascript
test.concurrent.only.each([[1, 2, 3], [2, 3, 5], [3, 4, 7]])(
  'add(%i, %i)',
  async (a, b, expected) => {
    await new Promise(r => setTimeout(r, 1000));
    expect(a + b).toBe(expected);
  }
);
```

### `test.concurrent.skip.each(table)(name, fn)`
Skips the specified concurrent tests with different data sets.

```javascript
test.concurrent.skip.each([[1, 2, 3], [2, 3, 5], [3, 4, 7]])(
  'add(%i, %i)',
  async (a, b, expected) => {
    await new Promise(r => setTimeout(r, 1000));
    expect(a + b).toBe(expected);
  }
);
```

### `test.each(table)(name, fn, timeout)`
Runs the same test with different data sets. `table` is an array of arrays with the test data.

```javascript
test.each([[1, 2, 3], [2, 3, 5], [3, 4, 7]])(
  'add(%i, %i) returns %i',
  (a, b, expected) => {
    expect(a + b).toBe(expected);
  }
);
```

### `test.failing(name, fn, timeout)`
Defines a test that is expected to fail. If the test does not fail, it is marked as a failure.

```javascript
test.failing('This test should fail', () => {
  expect(true).toBe(false);
});
```

### `test.failing.each(name, fn, timeout)`
Defines multiple tests that are expected to fail with different data sets.

```javascript
test.failing.each([[1, 2, 4], [2, 3, 6], [3, 4, 8]])(
  'add(%i, %i) should not return %i',
  (a, b, unexpected) => {
    expect(a + b).not.toBe(unexpected);
  }
);
```

### `test.only.failing(name, fn, timeout)`
Runs only the specified test that is expected to fail.

```javascript
test.only.failing('This test should fail', () => {
  expect(true).toBe(false);
});
```

### `test.skip.failing(name, fn, timeout)`
Skips the specified test that is expected to fail.

```javascript
test.skip.failing('This test should fail', () => {
  expect(true).toBe(false);
});
```

### `test.only(name, fn, timeout)`
Runs only the specified test, ignoring all other tests.

```javascript
test.only('Only this test runs', () => {
  expect(1 + 1).toBe(2);
});
```

### `test.only.each(table)(name, fn)`
Runs only the specified test with different data sets.

```javascript
test.only.each([[1, 2, 3], [2, 3, 5], [3, 4, 7]])(
  'add(%i, %i) returns %i',
  (a, b, expected) => {
    expect(a + b).toBe(expected);
  }
);
```

### `test.skip(name, fn)`
Skips the specified test.

```javascript
test.skip('This test is skipped', () => {
  expect(1 + 1).toBe(2);
});
```

### `test.skip.each(table)(name, fn)`
Skips the specified test with different data sets.

```javascript
test.skip.each([[1, 2, 3], [2, 3, 5], [3, 4, 7]])(
  'add(%i, %i) returns %i',
  (a, b, expected) => {
    expect(a + b).toBe(expected);
  }
);
```

### `test.todo(name)`
Marks a test as "to do". The test will appear in the test results as a placeholder for a future test.

```javascript
test.todo('This test needs to be written');
```

These Jest functions and methods allow for flexible and powerful testing capabilities, making it easier to structure and manage your tests.