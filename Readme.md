# Jest: is a delightful JavaScript Testing Framework with a focus on simplicity.

### Installation
``` bash
npm i -D jest
```
### Configuration
``` bash
 npm init jest@latest
```
### Check all the initial setup prompts
<img src='./jest_init.png' height="200px">

## [jest.config.js](jest.config.md) &#128072;
```javascript
/** @type {import('jest').Config} */
const config = {
    // You can unComments the feature that you want in your project and also customize according to your need 
}
module.exports=config
```
 * For a detailed explanation regarding each configuration property, visit: <br/>
  https://jestjs.io/docs/configuration
 
------------------------------------------------------------------------------------
* All imported modules in your tests should be mocked automatically
  ```bash 
  automock: false,
  ```
## Configure Jest With eslint
[```.eslintrc.json``` File#](./eslintrc.json) &#128072;

Jest can be used with ESLint without any further configuration as long as you import the [Jest global helpers](https://jestjs.io/docs/api) `(describe, it, etc.)` from `@jest/globals` before using them in your test file. This is necessary to avoid no-undef errors from ESLint, which doesn't know about the Jest globals.

If you'd like to avoid these imports, you can configure your [ESLint environment](https://eslint.org/docs/latest/use/configure/language-options#specifying-environments) to support these globals by adding the jest environment:
```json
{
  "overrides": [
    {
      "files": ["tests/**/*"],
      "env": {
        "jest": true
      }
    }
  ]
}
```
Or use [eslint-plugin-jest](https://github.com/jest-community/eslint-plugin-jest), which has a similar effect:
```json
{
  "overrides": [
    {
      "files": ["tests/**/*"],
      "plugins": ["jest"],
      "env": {
        "jest/globals": true
      }
    }
  ]
}
```
### [Go For eslint more Configurations](./eslintConfig.md) &#128072;

