# Jest Objects [For More Information](https://jestjs.io/docs/jest-object)&#128072;

This document organizes various Jest methods into categories for easier reference.

## Mock Modules

Methods for mocking modules, enabling or disabling automocking, and working with mock instances.

- `jest.disableAutomock()`: Disables automatic mocking in the Jest environment.
- `jest.enableAutomock()`: Enables automatic mocking in the Jest environment.
- `jest.createMockFromModule(moduleName)`: Generates a mock module based on the given module name.
- `jest.mock(moduleName, factory, options)`: Mocks a module with an optional factory and options.
- `jest.Mocked<Source>`: A utility type for TypeScript users to mark all methods of an object as mocked.
- `jest.mocked(source, options?)`: A utility function for TypeScript users to ensure types are correct for mocked functions.
- `jest.unmock(moduleName)`: Indicates that the given module should not be mocked.
- `jest.deepUnmock(moduleName)`: Indicates that the given module and all of its dependencies should not be mocked.
- `jest.doMock(moduleName, factory, options)`: Mocks a module with an optional factory and options, but only for the current file.
- `jest.dontMock(moduleName)`: Indicates that the given module should not be mocked, but only for the current file.
- `jest.setMock(moduleName, moduleExports)`: Explicitly sets the mock content of a module.
- `jest.requireActual(moduleName)`: Returns the actual module instead of a mock, bypassing all mocking mechanisms.
- `jest.requireMock(moduleName)`: Returns the mock version of a module.
- `jest.resetModules()`: Resets the module registry - the cache of all required modules.
- `jest.isolateModules(fn)`: Isolates the execution of the given function to its own module registry.
- `jest.isolateModulesAsync(fn)`: Asynchronously isolates the execution of the given function to its own module registry.

## Mock Functions

Methods for creating and working with mock functions.

- `jest.fn(implementation?)`: Creates a new mock function, optionally with a specific implementation.
- `jest.isMockFunction(fn)`: Determines if the given function is a mock function.
- `jest.replaceProperty(object, propertyKey, value)`: Replaces a property of an object with a given value, useful for mocking.
- `jest.spyOn(object, methodName)`: Creates a mock function similar to `jest.fn` but also tracks calls to `object[methodName]`.
- `jest.spyOn(object, methodName, accessType?)`: Additionally allows spying on getter/setter access types.
- `jest.Replaced<Source>`: A utility type for TypeScript users to mark all methods of an object as replaced.
- `jest.Spied<Source>`: A utility type for TypeScript users to mark all methods of an object as spied upon.
- `jest.clearAllMocks()`: Clears all information stored in all mock function instances.
- `jest.resetAllMocks()`: Resets all information stored in all mock function instances and restores their original (non-mocked) implementations.
- `jest.restoreAllMocks()`: Restores all mocks back to their original value.

## Fake Timers

Methods for controlling and manipulating the JavaScript timer functions.

- `jest.useFakeTimers(fakeTimersConfig?)`: Configures Jest to use fake timers for functions like `setTimeout`.
- `jest.useRealTimers()`: Configures Jest to use the real native timer functions.
- `jest.runAllTicks()`: Exhausts the micro-task queue (process.nextTick).
- `jest.runAllTimers()`: Advances all timers to their next steps.
- `jest.runAllTimersAsync()`: Asynchronously advances all timers to their next steps.
- `jest.runAllImmediates()`: Executes all tasks scheduled with `setImmediate`.
- `jest.advanceTimersByTime(msToRun)`: Advances timers by the specified time.
- `jest.advanceTimersByTimeAsync(msToRun)`: Asynchronously advances timers by the specified time.
- `jest.runOnlyPendingTimers()`: Executes only the timers that are currently pending.
- `jest.runOnlyPendingTimersAsync()`: Asynchronously executes only the timers that are currently pending.
- `jest.advanceTimersToNextTimer(steps)`: Advances timers to the next set timer.
- `jest.advanceTimersToNextTimerAsync(steps)`: Asynchronously advances timers to the next set timer.
- `jest.clearAllTimers()`: Clears all timers.
- `jest.getTimerCount()`: Returns the number of timers currently scheduled.
- `jest.now()`: Returns the current time according to the fake timers.
- `jest.setSystemTime(now?: number | Date)`: Sets the current system time for fake timers.
- `jest.getRealSystemTime()`: Gets the real system time.

## Misc

Miscellaneous methods for configuring Jest or retrieving information.

- `jest.getSeed()`: Returns the random seed used by Jest's test runner.
- `jest.isEnvironmentTornDown()`: Checks if the Jest environment has been torn down.
- `jest.retryTimes(numRetries, options?)`: Sets the number of times Jest should retry a test before it is considered failed.
- `jest.setTimeout(timeout)`: Sets the default timeout interval for tests and before/after hooks.

```javascript
// Mock Modules
jest.disableAutomock(); // Disables automatic mocking.
jest.enableAutomock(); // Enables automatic mocking.
jest.createMockFromModule('moduleName'); // Creates a mock from a module.
jest.mock('moduleName', () => ({}), {virtual: true}); // Mocks a module.
const mockedSource = jest.Mocked<Source>; // TypeScript utility type for mocking.
jest.mocked(source, {deep: true}); // Ensures types are correct for mocked functions.
jest.unmock('moduleName'); // Stops mocking a module.
jest.deepUnmock('moduleName'); // Stops mocking a module and its dependencies.
jest.doMock('moduleName', () => ({}), {virtual: true}); // Mocks a module for the current file.
jest.dontMock('moduleName'); // Stops mocking a module for the current file.
jest.setMock('moduleName', {}); // Sets mock content for a module.
const actualModule = jest.requireActual('moduleName'); // Gets the actual module.
const mockModule = jest.requireMock('moduleName'); // Gets the mock version of a module.
jest.resetModules(); // Resets the module registry.
jest.isolateModules(() => {}); // Isolates module execution.
jest.isolateModulesAsync(async () => {}); // Asynchronously isolates module execution.

// Mock Functions
const mockFn = jest.fn(() => true); // Creates a mock function.
const isMockFn = jest.isMockFunction(() => {}); // Checks if a function is a mock function.
jest.replaceProperty(object, 'propertyKey', 'value'); // Replaces an object's property.
const spy = jest.spyOn(object, 'methodName'); // Creates a spy on a method.
const spyWithAccessType = jest.spyOn(object, 'methodName', 'get'); // Spies on a getter method.
const replacedSource = jest.Replaced<Source>; // TypeScript utility type for replaced properties.
const spiedSource = jest.Spied<Source>; // TypeScript utility type for spied properties.
jest.clearAllMocks(); // Clears all mocks.
jest.resetAllMocks(); // Resets all mocks.
jest.restoreAllMocks(); // Restores all mocks.

// Fake Timers
jest.useFakeTimers(); // Uses fake timers.
jest.useRealTimers(); // Uses real timers.
jest.runAllTicks(); // Runs all ticks.
jest.runAllTimers(); // Runs all timers.
jest.runAllTimersAsync(); // Runs all timers asynchronously.
jest.runAllImmediates(); // Runs all immediates.
jest.advanceTimersByTime(1000); // Advances timers by time.
jest.advanceTimersByTimeAsync(1000); // Asynchronously advances timers by time.
jest.runOnlyPendingTimers(); // Runs only pending timers.
jest.runOnlyPendingTimersAsync(); // Asynchronously runs only pending timers.
jest.advanceTimersToNextTimer(2); // Advances timers to the next timer.
jest.advanceTimersToNextTimerAsync(2); // Asynchronously advances timers to the next timer.
jest.clearAllTimers(); // Clears all timers.
const timerCount = jest.getTimerCount(); // Gets the timer count.
const now = jest.now(); // Gets the current time in the context of fake timers.
jest.setSystemTime(new Date()); // Sets the system time.
const realSystemTime = jest.getRealSystemTime(); // Gets the real system time.

// Misc
const seed = jest.getSeed(); // Gets the seed used by Jest's random number generator.
const isEnvironmentTornDown = jest.isEnvironmentTornDown(); // Checks if the environment is torn down.
jest.retryTimes(3); // Sets the number of times to retry a test.
jest.setTimeout(10000); // Sets the timeout for a test.
```
