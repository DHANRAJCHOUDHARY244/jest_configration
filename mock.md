# Mocks In Jest [For More INformation Go To](https://jestjs.io/docs/mock-function-api)&#128072;

- mockFn.getMockName()
- mockFn.mock.calls
- mockFn.mock.results
- mockFn.mock.instances
- mockFn.mock.contexts
- mockFn.mock.lastCall
- mockFn.mockClear()
- mockFn.mockReset()
- mockFn.mockRestore()
- mockFn.mockImplementation(fn)
- mockFn.mockImplementationOnce(fn)
- mockFn.mockName(name)
- mockFn.mockReturnThis()
- mockFn.mockReturnValue(value)
- mockFn.mockReturnValueOnce(value)
- mockFn.mockResolvedValue(value)
- mockFn.mockResolvedValueOnce(value)
- mockFn.mockRejectedValue(value)
- mockFn.mockRejectedValueOnce(value)
- mockFn.withImplementation(fn, callback)




### Step 1: Define Functions

#### Normal (Synchronous) Function
A simple addition function.

```javascript
function add(a, b) {
  return a + b;
}
```

#### Asynchronous Function
A function that simulates fetching data with a delay.

```javascript
function fetchData() {
  return new Promise((resolve) => {
    setTimeout(() => resolve("data"), 1000);
  });
}
```

### Step 2: Mocking with Jest

#### Mocking the Synchronous Function
We'll start by mocking the `add` function.

```javascript
// Mocking the add function
const addMock = jest.fn(add);

// Example usage
addMock(2, 3);
console.log(addMock.mock.calls); // Output: [[2, 3]]
console.log(addMock.mock.results); // Output: [{ type: 'return', value: 5 }]
```

#### Mocking the Asynchronous Function
Now, let's mock the `fetchData` function.

```javascript
// Mocking the fetchData function
const fetchDataMock = jest.fn(fetchData);

// Mocking a resolved value
fetchDataMock.mockResolvedValue("mocked data");

// Example usage
fetchDataMock().then(data => console.log(data)); // Output: mocked data
```

### Step 3: Demonstrating Specific Mock Functions

#### `mockFn.mockResolvedValue(value)` and `mockFn.mockResolvedValueOnce(value)`
These are particularly useful for mocking asynchronous functions like `fetchData`.

```javascript
fetchDataMock.mockResolvedValueOnce("first call data");
fetchDataMock().then(data => console.log(data)); // Output: first call data
fetchDataMock().then(data => console.log(data)); // Output: mocked data
```

#### `mockFn.mockRejectedValue(value)` and `mockFn.mockRejectedValueOnce(value)`
To simulate a failure in an asynchronous operation:

```javascript
fetchDataMock.mockRejectedValueOnce(new Error("Failed to fetch"));
fetchDataMock().catch(error => console.log(error.message)); // Output: Failed to fetch
```

#### Using `mockFn.mockImplementation(fn)` and `mockFn.mockImplementationOnce(fn)` for Asynchronous Functions
You can also dynamically change the implementation of an asynchronous function.

```javascript
fetchDataMock.mockImplementationOnce(() => Promise.resolve("dynamic data"));
fetchDataMock().then(data => console.log(data)); // Output: dynamic data
```

This example demonstrates how to create and mock both synchronous and asynchronous functions using Jest, showcasing the versatility of Jest's mocking capabilities to simulate different behaviors and scenarios in our tests.