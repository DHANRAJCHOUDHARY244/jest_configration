## Jest Compenents
```
                                    JEST                                       
          ___________________________|_____________________________                
         |           |          |        |          |              |
    Globals   Jest Objects    Expect  Jest Mock  Jest Cli   Jest Configure

```

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|| &nbsp;&nbsp;[Globals](./globals.md) &nbsp;&nbsp; ||  &nbsp;&nbsp;[EslintConfig](./eslintConfig.md) &nbsp;&nbsp;|| &nbsp;&nbsp;[Expect](./matchers.md)&nbsp;&nbsp;||&nbsp;&nbsp;[Mocks](./mock.md)&nbsp;&nbsp;||&nbsp;&nbsp;[Jest Objects](./jestObjects.md)&nbsp;&nbsp;||&nbsp;&nbsp;[Jest Cli](./jestCli.md)&nbsp;&nbsp;||&nbsp;&nbsp;[Jest Configure](./jest.config.md) &nbsp;&nbsp;&nbsp;&nbsp;||

## jest.setup.js
### run before test and run mongo server and set environment variables till jest executation not complete

```javascript
const dotenv = require("dotenv");

// Path to your .env.test file
dotenv.config({ path: ".env.test" });
// Connect to MongoDB
require("mongoose")
  .connect(process.env.DB_URI)
  .catch((err) => {
    console.error("Error connecting to MongoDB", err);
    process.exit(1);
  });
```

---

## jest.teardown.js
### execute after jest testcases complete
```javascript
const mongoose = require("mongoose");
const { exec } = require("child_process");

module.exports = async () => {
  await mongoose.connection.close();
  await mongoose.disconnect();
  const reportPath = "./reports/jest-stare/index.html";
  switch (process.platform) {
    case "darwin": // macOS
      exec(`open ${reportPath}`);
      break;
    case "win32": // Windows
      exec(`start ${reportPath}`);
      break;
    default: // Linux and others
      exec(`xdg-open ${reportPath}`);
      break;
  }
  process.exit(0);
};
```

---

## jest.config.js

```javascript
/**
 * For a detailed explanation regarding each configuration property, visit:
 * https://jestjs.io/docs/configuration
 */

/** @type {import('jest').Config} */
const config = {
  // All imported modules in your tests should be mocked automatically
  // automock: false,

  // Stop running tests after `n` failures
  // bail: 0,

  // The directory where Jest should store its cached dependency information
  // cacheDirectory: "/tmp/jest_rt",

  // Automatically clear mock calls, instances, contexts and results before every test
  clearMocks: true,

  // Indicates which provider should be used to instrument code for coverage
  coverageProvider: "v8",

  // A list of reporter names that Jest uses when writing coverage reports
  coverageReporters: ["json", "text", "lcov", "clover"],

  // An array of directory names to be searched recursively up from the requiring module's location
  moduleDirectories: ["node_modules"],

  // An array of file extensions your modules use
  moduleFileExtensions: [
    "js",
    "mjs",
    "cjs",
    //   "jsx",
    //   "ts",
    //   "tsx",
    "json",
    "node",
  ],
  // Indicates whether the coverage information should be collected while executing the test
  collectCoverage: true,

  // The directory where Jest should output its coverage files
  coverageDirectory: "./reports/coverage",

  // Use this configuration option to add custom reporters to Jest
  reporters: [
    "default",
    [
      "jest-stare",
      {
        resultDir: "reports/jest-stare",
        reportTitle: "jest-stare!",
        additionalResultsProcessors: ["jest-junit"],
        coverageLink: "../coverage/lcov-report/index.html",
        jestStareConfigJson: "jest-stare.json",
        jestGlobalConfigJson: "globalStuff.json",
      },
    ],
  ],

  // The glob patterns Jest uses to detect test files
  testMatch: ["**/__tests__/**/*.[jt]s?(x)", "**/?(*.)+(spec|test).[tj]s?(x)"],

  // An array of regexp pattern strings that are matched against all test paths, matched tests are skipped
  testPathIgnorePatterns: ["/node_modules/"],

  // Whether to use watchman for file crawling
  watchman: false,

  // Path to setup file
  setupFiles: ["./jest.setup.js"], // Adjust the path according to where you placed your setup file
  globalTeardown: "./jest.teardown.js",
};

module.exports = config;
```
# For More Configurations
```javascript
/** @type {import('jest').Config} */
const config = {
  // All imported modules in your tests should be mocked automatically
  automock: false,

  // Stop running tests after `n` failures
  bail: 1,

  // The directory where Jest should store its cached dependency information
  cacheDirectory: "/tmp/jest_rt",

  // Automatically clear mock calls, instances, contexts and results before every test
  clearMocks: true,

  // Indicates whether the coverage information should be collected while executing the test
  collectCoverage: true,

  // An array of glob patterns indicating a set of files for which coverage information should be collected
  collectCoverageFrom: ["src/**/*.{js,jsx,ts,tsx}"],

  // The directory where Jest should output its coverage files
  coverageDirectory: "coverage",

  // An array of regexp pattern strings used to skip coverage collection
  coveragePathIgnorePatterns: ["/node_modules/", "/tests/"],

  // Indicates which provider should be used to instrument code for coverage
  coverageProvider: "v8",

  // A list of reporter names that Jest uses when writing coverage reports
  coverageReporters: ["json", "text", "lcov", "clover"],

  // An object that configures minimum threshold enforcement for coverage results
  coverageThreshold: {
    global: {
      branches: 80,
      functions: 80,
      lines: 80,
      statements: 80,
    },
  },

  // A path to a custom dependency extractor
  dependencyExtractor: "path/to/dependencyExtractor.js",

  // Make calling deprecated APIs throw helpful error messages
  errorOnDeprecated: true,

  // The default configuration for fake timers
  fakeTimers: {
    enableGlobally: true,
  },

  // Force coverage collection from ignored files using an array of glob patterns
  forceCoverageMatch: ["**/ignored/**"],

  // A path to a module which exports an async function that is triggered once before all test suites
  globalSetup: "./globalSetup.js",

  // A path to a module which exports an async function that is triggered once after all test suites
  globalTeardown: "./globalTeardown.js",

  // A set of global variables that need to be available in all test environments
  globals: {
    __DEV__: true,
  },

  // The maximum amount of workers used to run your tests
  maxWorkers: "50%",

  // An array of directory names to be searched recursively up from the requiring module's location
  moduleDirectories: ["node_modules", "src"],

  // An array of file extensions your modules use
  moduleFileExtensions: ["js", "jsx", "ts", "tsx", "json", "node"],

  // A map from regular expressions to module names or to arrays of module names that allow to stub out resources with a single module
  moduleNameMapper: {
    "^@src/(.*)$": "<rootDir>/src/$1",
  },

  // An array of regexp pattern strings, matched against all module paths before considered 'visible' to the module loader
  modulePathIgnorePatterns: ["/dist/"],

  // Activates notifications for test results
  notify: true,

  // An enum that specifies notification mode
  notifyMode: "failure-change",

  // A preset that is used as a base for Jest's configuration
  preset: "ts-jest",

  // Run tests from one or more projects
  projects: ["<rootDir>/project1", "<rootDir>/project2"],

  // Use this configuration option to add custom reporters to Jest
  reporters: ["default", "jest-junit"],

  // Automatically reset mock state before every test
  resetMocks: true,

  // Reset the module registry before running each individual test
  resetModules: true,

  // A path to a custom resolver
  resolver: "path/to/customResolver.js",

  // Automatically restore mock state and implementation before every test
  restoreMocks: true,

  // The root directory that Jest should scan for tests and modules within
  rootDir: "./",

  // A list of paths to directories that Jest should use to search for files in
  roots: ["<rootDir>/src"],

  // Allows you to use a custom runner instead of Jest's default test runner
  runner: "jest-runner",

  // The paths to modules that run some code to configure or set up the testing environment before each test
  setupFiles: ["./setupFile.js"],

  // A list of paths to modules that run some code to configure or set up the testing framework before each test
  setupFilesAfterEnv: ["./setupTestFramework.js"],

  // The number of seconds after which a test is considered as slow and reported as such in the results
  slowTestThreshold: 5,

  // A list of paths to snapshot serializer modules Jest should use for snapshot testing
  snapshotSerializers: ["enzyme-to-json/serializer"],

  // The test environment that will be used for testing
  testEnvironment: "jest-environment-node",

  // Options that will be passed to the testEnvironment
  testEnvironmentOptions: {
    userAgent: "node.js",
  },

  // Adds a location field to test results
  testLocationInResults: true,

  // The glob patterns Jest uses to detect test files
  testMatch: ["**/__tests__/**/*.[jt]s?(x)", "**/?(*.)+(spec|test).[tj]s?(x)"],

  // An array of regexp pattern strings that are matched against all test paths, matched tests are skipped
  testPathIgnorePatterns: ["/node_modules/", "/dist/"],

  // The regexp pattern or array of patterns that Jest uses to detect test files
  testRegex: [],

  // This option allows the use of a custom results processor
  testResultsProcessor: "jest-sonar-reporter",

  // This option allows use of a custom test runner
  testRunner: "jest-circus/runner",

  // A map from regular expressions to paths to transformers
  transform: {
    "^.+\\.jsx?$": "babel-jest",
    "^.+\\.tsx?$": "ts-jest",
  },

  // An array of regexp pattern strings that are matched against all source file paths, matched files will skip transformation
  transformIgnorePatterns: ["/node_modules/", "\\.pnp\\.[^\\/]+$"],

  // An array of regexp pattern strings that are matched against all modules before the module loader will automatically return a mock for them
  unmockedModulePathPatterns: ["/node_modules/react/"],

  // Indicates whether each individual test should be reported during the run
  verbose: true,

  // An array of regexp patterns that are matched against all source file paths before re-running tests in watch mode
  watchPathIgnorePatterns: ["<rootDir>/node_modules/"],

  // Whether to use watchman for file crawling
  watchman: true,
};

module.exports = config;
```
