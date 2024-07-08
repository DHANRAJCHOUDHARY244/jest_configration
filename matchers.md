## Jest Compenents
```
                                    JEST                                       
          ___________________________|_____________________________                
         |           |          |        |          |              |
    Globals   Jest Objects    Expect  Jest Mock  Jest Cli   Jest Configure

```

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|| &nbsp;&nbsp;[Globals](./globals.md) &nbsp;&nbsp; ||  &nbsp;&nbsp;[EslintConfig](./eslintConfig.md) &nbsp;&nbsp;|| &nbsp;&nbsp;[Expect](./matchers.md)&nbsp;&nbsp;||&nbsp;&nbsp;[Mocks](./mock.md)&nbsp;&nbsp;||&nbsp;&nbsp;[Jest Objects](./jestObjects.md)&nbsp;&nbsp;||&nbsp;&nbsp;[Jest Cli](./jestCli.md)&nbsp;&nbsp;||&nbsp;&nbsp;[Jest Configure](./jest.config.md) &nbsp;&nbsp;&nbsp;&nbsp;||

- `expect(value)`
  - Modifiers:
    - `.not`
    - `.resolves`
    - `.rejects`
  - Matchers:
    - `.toBe(value)`
    - `.toHaveBeenCalled()`
    - `.toHaveBeenCalledTimes(number)`
    - `.toHaveBeenCalledWith(arg1, arg2, ...)`
    - `.toHaveBeenLastCalledWith(arg1, arg2, ...)`
    - `.toHaveBeenNthCalledWith(nthCall, arg1, arg2, ...)`
    - `.toHaveReturned()`
    - `.toHaveReturnedTimes(number)`
    - `.toHaveReturnedWith(value)`
    - `.toHaveLastReturnedWith(value)`
    - `.toHaveNthReturnedWith(nthCall, value)`
    - `.toHaveLength(number)`
    - `.toHaveProperty(keyPath, value?)`
    - `.toBeCloseTo(number, numDigits?)`
    - `.toBeDefined()`
    - `.toBeFalsy()`
    - `.toBeGreaterThan(number | bigint)`
    - `.toBeGreaterThanOrEqual(number | bigint)`
    - `.toBeLessThan(number | bigint)`
    - `.toBeLessThanOrEqual(number | bigint)`
    - `.toBeInstanceOf(Class)`
    - `.toBeNull()`
    - `.toBeTruthy()`
    - `.toBeUndefined()`
    - `.toBeNaN()`
    - `.toContain(item)`
    - `.toContainEqual(item)`
    - `.toEqual(value)`
    - `.toMatch(regexp | string)`
    - `.toMatchObject(object)`
    - `.toMatchSnapshot(propertyMatchers?, hint?)`
    - `.toMatchInlineSnapshot(propertyMatchers?, inlineSnapshot)`
    - `.toStrictEqual(value)`
    - `.toThrow(error?)`
    - `.toThrowErrorMatchingSnapshot(hint?)`
    - `.toThrowErrorMatchingInlineSnapshot(inlineSnapshot)`
  - Asymmetric Matchers:
    - `expect.anything()`
    - `expect.any(constructor)`
    - `expect.arrayContaining(array)`
    - `expect.not.arrayContaining(array)`
    - `expect.closeTo(number, numDigits?)`
    - `expect.objectContaining(object)`
    - `expect.not.objectContaining(object)`
    - `expect.stringContaining(string)`
    - `expect.not.stringContaining(string)`
    - `expect.stringMatching(string | regexp)`
    - `expect.not.stringMatching(string | regexp)`
  - Assertion Count:
    - `expect.assertions(number)`
    - `expect.hasAssertions()`
  - Extend Utilities:
    - `expect.addEqualityTesters(testers)`
    - `expect.addSnapshotSerializer(serializer)`
    - `expect.extend(matchers)`

## For Examples

```javascript
// expect(value)
expect(2 + 2).toBe(4); // Example for `.toBe(value)`

// Modifiers
expect(2 + 2).not.toBe(5); // Example for `.not`

await expect(Promise.resolve("value")).resolves.toBe("value"); // Example for `.resolves`

await expect(Promise.reject("error")).rejects.toBe("error"); // Example for `.rejects`

// Matchers
expect(() => {}).toHaveBeenCalled(); // Example for `.toHaveBeenCalled()`

expect(() => {}).toHaveBeenCalledTimes(1); // Example for `.toHaveBeenCalledTimes(number)`

expect(() => {}).toHaveBeenCalledWith("arg1", "arg2"); // Example for `.toHaveBeenCalledWith(arg1, arg2, ...)`

expect(() => {}).toHaveBeenLastCalledWith("arg1", "arg2"); // Example for `.toHaveBeenLastCalledWith(arg1, arg2, ...)`

expect(() => {}).toHaveBeenNthCalledWith(1, "arg1", "arg2"); // Example for `.toHaveBeenNthCalledWith(nthCall, arg1, arg2, ...)`

expect(() => {}).toHaveReturned(); // Example for `.toHaveReturned()`

expect(() => {}).toHaveReturnedTimes(1); // Example for `.toHaveReturnedTimes(number)`

expect(() => {}).toHaveReturnedWith("value"); // Example for `.toHaveReturnedWith(value)`

expect(() => {}).toHaveLastReturnedWith("value"); // Example for `.toHaveLastReturnedWith(value)`

expect(() => {}).toHaveNthReturnedWith(1, "value"); // Example for `.toHaveNthReturnedWith(nthCall, value)`

expect([1, 2, 3]).toHaveLength(3); // Example for `.toHaveLength(number)`

expect({ name: "John" }).toHaveProperty("name", "John"); // Example for `.toHaveProperty(keyPath, value?)`

expect(3.14159).toBeCloseTo(Math.PI, 2); // Example for `.toBeCloseTo(number, numDigits?)`

expect({}.prop).toBeDefined(); // Example for `.toBeDefined()`

expect(false).toBeFalsy(); // Example for `.toBeFalsy()`

expect(10).toBeGreaterThan(5); // Example for `.toBeGreaterThan(number | bigint)`

expect(10).toBeGreaterThanOrEqual(10); // Example for `.toBeGreaterThanOrEqual(number | bigint)`

expect(5).toBeLessThan(10); // Example for `.toBeLessThan(number | bigint)`

expect(5).toBeLessThanOrEqual(5); // Example for `.toBeLessThanOrEqual(number | bigint)`

expect(new Error()).toBeInstanceOf(Error); // Example for `.toBeInstanceOf(Class)`

expect(null).toBeNull(); // Example for `.toBeNull()`

expect(true).toBeTruthy(); // Example for `.toBeTruthy()`

expect(undefined).toBeUndefined(); // Example for `.toBeUndefined()`

expect(NaN).toBeNaN(); // Example for `.toBeNaN()`

expect([1, 2, 3]).toContain(2); // Example for `.toContain(item)`

expect([{ name: "John" }]).toContainEqual({ name: "John" }); // Example for `.toContainEqual(item)`

expect({ name: "John" }).toEqual({ name: "John" }); // Example for `.toEqual(value)`

expect("Christoph").toMatch(/stop/); // Example for `.toMatch(regexp | string)`

expect({ name: "John" }).toMatchObject({ name: "John" }); // Example for `.toMatchObject(object)`

expect({ name: "John" }).toMatchSnapshot(); // Example for `.toMatchSnapshot(propertyMatchers?, hint?)`

expect({ name: "John" }).toMatchInlineSnapshot(); // Example for `.toMatchInlineSnapshot(propertyMatchers?, inlineSnapshot)`

expect({ name: "John" }).toStrictEqual({ name: "John" }); // Example for `.toStrictEqual(value)`

expect(() => {
  throw new Error("error");
}).toThrow("error"); // Example for `.toThrow(error?)`

expect(() => {
  throw new Error("error");
}).toThrowErrorMatchingSnapshot(); // Example for `.toThrowErrorMatchingSnapshot(hint?)`

expect(() => {
  throw new Error("error");
}).toThrowErrorMatchingInlineSnapshot(); // Example for `.toThrowErrorMatchingInlineSnapshot(inlineSnapshot)`

// Asymmetric Matchers

expect(null).not.toEqual(expect.anything()); // Example for `expect.anything()`

expect("hello").toEqual(expect.any(String)); // Example for `expect.any(constructor)`

expect(["Alice", "Bob", "Eve"]).toEqual(
  expect.arrayContaining(["Alice", "Bob"])
); // Example for `expect.arrayContaining(array)`

expect(["Alice", "Bob"]).not.toEqual(expect.arrayContaining(["Eve"])); // Example for `expect.not.arrayContaining(array)`

expect(3.14).toEqual(expect.closeTo(Math.PI, 2)); // Example for `expect.closeTo(number, numDigits?)`

expect({ name: "John", age: 30 }).toEqual(
  expect.objectContaining({ name: "John" })
); // Example for `expect.objectContaining(object)`

expect({ name: "John" }).not.toEqual(expect.objectContaining({ age: 30 })); // Example for `expect.not.objectContaining(object)`

expect("Hello world").toEqual(expect.stringContaining("world")); // Example for `expect.stringContaining(string)`

expect("Hello world").not.toEqual(expect.stringContaining("bye")); // Example for `expect.not.stringContaining(string)`

expect("Christoph").toEqual(expect.stringMatching(/stop/)); // Example for `expect.stringMatching(string | regexp)`

expect("Christoph").not.toEqual(expect.stringMatching(/fail/)); // Example for `expect.not.stringMatching(string | regexp)`

// Assertion Count
expect.assertions(2); // Example for `expect.assertions(number)`
expect.hasAssertions(); // Example for `expect.hasAssertions()`

// Extend Utilities
expect.extend({
  toBeDivisibleBy(received, argument) {
    const pass = received % argument === 0;
    if (pass) {
      return {
        message: () =>
          `expected ${received} not to be divisible by ${argument}`,
        pass: true,
      };
    } else {
      return {
        message: () => `expected ${received} to be divisible by ${argument}`,
        pass: false,
      };
    }
  },
}); // Example for `expect.extend(matchers)`
expect(100).toBeDivisibleBy(25); // Usage of custom matcher
```

## [For More Information Go To](https://jestjs.io/docs/expect)&#128072;