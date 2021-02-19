# ISBN Verify

[![npm version](https://badge.fury.io/js/%40saekitominaga%2Fisbn-verify.svg)](https://badge.fury.io/js/%40saekitominaga%2Fisbn-verify)
[![Build Status](https://www.travis-ci.com/SaekiTominaga/isbn-verify.svg)](https://www.travis-ci.com/SaekiTominaga/isbn-verify)
[![Coverage Status](https://coveralls.io/repos/github/SaekiTominaga/isbn-verify/badge.svg)](https://coveralls.io/github/SaekiTominaga/isbn-verify)

Verify ISBN string format and check digit.

## Demo

- [Demo page](https://saekitominaga.github.io/isbn-verify/demo.html)

## Examples

```JavaScript
import ISBN from '@saekitominaga/isbn-verify';

const isbn = new ISBN('978-4-06-519981-0');
isbn.isValid(); // false
isbn.isIsbn10(); // false
isbn.isIsbn13(); // true
isbn.verifyFormat(); // true
isbn.verifyCheckDigit(); // false
```

## Constructor

```TypeScript
new ISBN(isbn: string, strict = false)
```

### Parameters

<dl>
<dt>isbn</dt>
<dd>ISBN value to check</dd>
<dt>strict [Optional]</dt>
<dd>Strict mode. If `true`, syntax without hyphens is an error. If not specified, it defaults to `false`.</dd>
</dl>

## Methods

| Name | Returns | Description |
|-|-|-|
| isValid() | {boolean} `true` if both format and check digit are correct | Alias of `verifyCheckDigit()` |
| isIsbn13() | {boolean} `true` for current standard (13 digit) ISBN | Whether it is a 13-digit ISBN |
| isIsbn10() | {boolean} `true` for old standard (10 digit) ISBN | Whether it is a 10-digit ISBN |
| verifyFormat() | {boolean} `true` if the format is correct | Verify format (do not verify check digit) |
| verifyCheckDigit() | {boolean} `true` if both format and check digit are correct | Verify format including check digit (not necessarily applicable publication |
