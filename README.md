# Simple padding lib for nodejs

Nothing more than simple padding function for Node.js  
It created by personal demand for reusing function for common use-case.

## Install

``npm install --save simple-padding``

## Usage

```javascript
const padding = require("simple-padding")

// "0000000001"
var integerPaddingBy0 = padding(1, 10)

// "      0.01"
var floatNum = padding(0.01, 10, " ")

// "0000000abc"
var defaultPaddingBy0 = padding("abc", 10)

// "aaaaaaa100"
var charPadding = padding(100, 10, "a")

// "000000-100"
var minusInt = padding(-100, 10, "0")

// "02147483647"
var intMaxPlusPad = padding(2147483647, 11)

// And you can take a look into various usecase in example.js ...
```

## Interface

```javascript
/**
 *
 * @param value input value
 * @param length index length
 * @param char [optional] char will be 0 when it is null or undefined.
 * @returns {string}
 */
function padding(value, length, char) {
    return String
}
```

## Error handling

```javascript
try {
    // Missing char
    padding("abc", 10, "")
    // Invalid 2nd param (padded length)
    padding("aaa", 0)
    // etc ..
} catch (e) {
    console.error(e);
}
```

## Contribution

- npm test
- npm test -- --watch
- Please create PR or Issue.

## Publish

```
git tag -a v1.0.0 -m "v1.0.0"
git push origin tags/v1.0.0
git tag
npm publish --access public .
```

## Update

npm version patch npm publish ./ 
