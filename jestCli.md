### Jest CLI Options

1. **jest \<regexForTestFiles\>**

   - Runs tests that match the specified regex pattern for test files.

   ```bash
   jest '.*\.test\.js$'
   ```

2. **--bail[=<n>]**

   - Exit after the first test failure or after a specific number of failures (`n`).

   ```bash
   jest --bail=1
   ```

3. **--cache**

   - Enables Jest's integrated caching system to speed up execution.

   ```bash
   jest --cache
   ```

4. **--changedFilesWithAncestor**

   - Lists files changed since the last commit that are relevant to the current working directory.

   ```bash
   jest --changedFilesWithAncestor
   ```

5. **--changedSince**

   - Runs tests related to the changes since a specified commit hash, branch, or tag.

   ```bash
   jest --changedSince=main
   ```

6. **--ci**

   - Runs Jest in continuous integration mode, optimizing for CI environments.

   ```bash
   jest --ci
   ```

7. **--clearCache**

   - Clears Jest's cache directory and stops caching.

   ```bash
   jest --clearCache
   ```

8. **--clearMocks**

   - Clears all mock calls and instances before each test.

   ```bash
   jest --clearMocks
   ```

9. **--collectCoverageFrom=<glob>**

   - Gathers code coverage information from files matching the glob pattern.

   ```bash
   jest --collectCoverageFrom='src/**/*.js'
   ```

10. **--colors**

    - Enables or disables colorized output.

    ```bash
    jest --colors=false
    ```

11. **--config=<path>**

    - Specifies the path to the Jest configuration file.

    ```bash
    jest --config=jest.config.js
    ```

12. **--coverage[=<boolean>]**

    - Generates code coverage report after running tests.

    ```bash
    jest --coverage
    ```

13. **--coverageDirectory=<path>**

    - Specifies the directory where coverage reports are saved.

    ```bash
    jest --coverageDirectory=coverage
    ```

14. **--coverageProvider=<provider>**

    - Specifies the coverage provider (e.g., `babel`, `v8`).

    ```bash
    jest --coverageProvider=v8
    ```

15. **--debug**

    - Prints debug information about Jest's configuration.

    ```bash
    jest --debug
    ```

16. **--detectOpenHandles**

    - Detects and prints open handles preventing Jest from exiting.

    ```bash
    jest --detectOpenHandles
    ```

17. **--env=<environment>**

    - Specifies the test environment (e.g., `jsdom`, `node`).

    ```bash
    jest --env=node
    ```

18. **--errorOnDeprecated**

    - Throws an error for deprecated usage.

    ```bash
    jest --errorOnDeprecated
    ```

19. **--expand**

    - Expands test result output to show full diffs.

    ```bash
    jest --expand
    ```

20. **--filter=<file>**

    - Runs tests that match the specified file filter.

    ```bash
    jest --filter=Login.test.js
    ```

21. **--findRelatedTests \<spaceSeparatedListOfSourceFiles\>**

    - Finds and runs tests related to the specified source files.

    ```bash
    jest --findRelatedTests src/Login.js src/Auth.js
    ```

22. **--forceExit**

    - Forces Jest to exit after all tests have completed.

    ```bash
    jest --forceExit
    ```

23. **--help**

    - Displays help information about Jest CLI options.

    ```bash
    jest --help
    ```

24. **--ignoreProjects \<project1\> ... \<projectN\>**

    - Ignores specified projects in a multi-project setup.

    ```bash
    jest --ignoreProjects=project1 project2
    ```

25. **--init**

    - Interactively creates a Jest configuration file.

    ```bash
    jest --init
    ```

26. **--injectGlobals**

    - Injects Jest globals like `jest` and `describe` into test files.

    ```bash
    jest --injectGlobals
    ```

27. **--json**

    - Outputs test results in JSON format.

    ```bash
    jest --json
    ```

28. **--lastCommit**

    - Runs tests related to files changed since the last commit.

    ```bash
    jest --lastCommit
    ```

29. **--listTests**

    - Lists all tests Jest will run without executing them.

    ```bash
    jest --listTests
    ```

30. **--logHeapUsage**

    - Logs heap usage after running tests.

    ```bash
    jest --logHeapUsage
    ```

31. **--maxConcurrency=<num>**

    - Sets maximum concurrent tests to run at once.

    ```bash
    jest --maxConcurrency=4
    ```

32. **--maxWorkers=<num>|\<string\>**

    - Sets the maximum number of workers Jest will spawn.

    ```bash
    jest --maxWorkers=2
    ```

33. **--noStackTrace**

    - Disables stack trace in test results.

    ```bash
    jest --noStackTrace
    ```

34. **--notify**

    - Enables desktop notifications on test completion.

    ```bash
    jest --notify
    ```

35. **--onlyChanged**

    - Runs tests related to files changed since the last commit.

    ```bash
    jest --onlyChanged
    ```

36. **--openHandlesTimeout=<milliseconds>**

    - Sets the timeout to wait for open handles to close.

    ```bash
    jest --openHandlesTimeout=3000
    ```

37. **--outputFile=<filename>**

    - Writes test results to a specified file.

    ```bash
    jest --outputFile=test-results.json
    ```

38. **--passWithNoTests**

    - Exits Jest with success even if no tests are found.

    ```bash
    jest --passWithNoTests
    ```

39. **--projects \<path1\> ... \<pathN\>**

    - Runs tests in specified project directories.

    ```bash
    jest --projects=project1 project2
    ```

40. **--randomize**

    - Runs tests in a random order.

    ```bash
    jest --randomize
    ```

41. **--reporters**

    - Specifies custom reporters for test output.

    ```bash
    jest --reporters=default
    ```

42. **--resetMocks**

    - Resets all mocks' state before each test.

    ```bash
    jest --resetMocks
    ```

43. **--restoreMocks**

    - Restores all mocked functions before each test.

    ```bash
    jest --restoreMocks
    ```

44. **--roots**

    - Specifies root directories for Jest to search for tests.

    ```bash
    jest --roots=src,test
    ```

45. **--runInBand**

    - Runs all tests serially in the current process.

    ```bash
    jest --runInBand
    ```

46. **--runTestsByPath**

    - Runs only tests matching the specified path.

    ```bash
    jest --runTestsByPath=src/Login.test.js
    ```

47. **--seed=<num>**

    - Specifies the seed for randomizing tests.

    ```bash
    jest --seed=123
    ```

48. **--selectProjects \<project1\> ... \<projectN\>**

    - Selects specified projects in a multi-project setup.

    ```bash
    jest --selectProjects=project1 project2
    ```

49. **--setupFilesAfterEnv \<path1\> ... \<pathN\>**

    - Specifies setup files to run after Jest's environment is set up.

    ```bash
    jest --setupFilesAfterEnv=./setupTests.js
    ```

50. **--shard**

    - Distributes tests across multiple shards.

    ```bash
    jest --shard
    ```

51. **--showConfig**

    - Displays Jest's configuration options and exits.

    ```bash
    jest --showConfig
    ```

52. **--showSeed**

    - Displays the Jest test seed and exits.

    ```bash
    jest --showSeed
    ```

53. **--silent**

    - Disables all console output during test execution.

    ```bash
    jest --silent
    ```

54. **--testEnvironmentOptions=<json string>**

    - Specifies options for the test environment.

    ```bash
    jest --testEnvironmentOptions='{"runInBand": true}'
    ```

55. **--testLocationInResults**

    - Includes test file locations in test result output.

    ```bash
    jest --testLocationInResults
    ```

56. **--testMatch \<glob1\> ... \<globN\>**

    - Specifies file patterns Jest should consider as tests.

    ```bash
    jest --testMatch='**/*.test.js'
    ```

57. **--testNamePattern=<regex>**

    - Runs only tests with names matching the specified regex pattern.

    ```bash
    jest --testNamePattern='Login'
    ```

58. **--testPathIgnorePatterns=<regex>|[array]**

    - Ignores files matching the specified regex patterns or paths.

    ```bash
    jest --testPathIgnorePatterns='__mocks__'
    ```

59. **--testPathPattern=<regex>**

    - Runs only tests with file paths matching the specified regex pattern.

    ```bash
    jest --testPathPattern='tests'
    ```

60. **--testRunner=<path>**

    - Specifies a custom test runner.

    ```bash
    jest --testRunner=./customTestRunner.js
    ```

61. **--testSequencer=<path>**

    - Specifies a custom test sequencer.

    ```bash
    jest --testSequencer=./customTestSequencer.js
    ```

62. **--testTimeout=<number>**

    - Sets the timeout for each test.

    ```bash
    jest --testTimeout=5000
    ```

63. **--updateSnapshot**

    - Updates failing snapshots during test runs.

    ```bash
    jest --updateSnapshot
    ```

64. **--useStderr**

    - Writes test results to stderr instead of stdout.

    ```bash
    jest --useStderr
    ```

65. **--verbose**

    - Displays verbose output.

    ```bash
    jest --verbose
    ```

66. **--version**

    - Displays Jest's version number.

    ```bash
    jest --version
    ```

67. **--watch**

    - Watches files and reruns tests on changes.

    ```bash
    jest --watch
    ```

68. **--watchAll**

    - Watches all files and reruns tests on changes.

    ```bash
    jest --watchAll
    ```

69. **--watchman**

    - Uses Watchman for watching file changes.

    ```bash
    jest --watchman
    ```

70. **--workerThreads**
    - Uses worker threads for running tests.
    ```bash
    jest --workerThreads
    ```

### Examples and Use Cases

Each option provides flexibility for configuring Jest according to specific testing requirements and environments. For example:

- **Running Tests with Coverage**:

  ```bash
  jest --coverage
  ```

- **Running Tests in Watch Mode**:

  ```bash
  jest --watch
  ```

- **Specifying Test Files**:

  ```bash
  jest '.*\.test\.js$'
  ```

- **Using a Custom Configuration File**:

  ```bash
  jest --config=jest.config.js
  ```

- **Running Tests in CI Mode**:

  ```bash
  jest --ci
  ```

- **Ignoring Projects**:

  ```bash
  jest --ignoreProjects=project1 project2
  ```

- **Generating JSON Output**:
  ```bash
  jest --json
  ```

These examples illustrate how Jest's CLI options can be leveraged to optimize testing workflows, manage test execution, and customize test behavior based on project needs. Adjust these options as necessary to fit specific testing strategies and environments effectively.
