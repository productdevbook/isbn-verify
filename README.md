# ISBN Verify

[![npm version](https://badge.fury.io/js/%40saekitominaga%2Fisbn-verify.svg)](https://badge.fury.io/js/%40saekitominaga%2Fisbn-verify)
[![Build Status](https://github.com/SaekiTominaga/isbn-verify/actions/workflows/test.yml/badge.svg)](https://github.com/SaekiTominaga/isbn-verify/actions/workflows/test.yml)
[![Coverage Status](https://coveralls.io/repos/github/SaekiTominaga/isbn-verify/badge.svg)](https://coveralls.io/github/SaekiTominaga/isbn-verify)

Verify ISBN string format and check digit.

## Demo

- [Demo page](https://saekitominaga.github.io/isbn-verify/demo.html)

## Examples

```JavaScript
import IsbnVerify from '@saekitominaga/isbn-verify';

const isbnVerify = new IsbnVerify('978-4-06-519981-0');
isbnVerify.isValid(); // false
isbnVerify.isIsbn10(); // false
isbnVerify.isIsbn13(); // true
isbnVerify.isIsbn13({ check_digit: true }); // false
isbnVerify.verifyFormat(); // true
isbnVerify.verifyCheckDigit(); // false
```

## Constructor

```TypeScript
new IsbnVerify(isbn: string, strict = false)
```

### Parameters

<dl>
<dt><code>isbn</code></dt>
<dd>ISBN value to check</dd>
<dt><code>strict</code> [Optional]</dt>
<dd>Strict mode. If `true`, syntax without hyphens is an error. If not specified, it defaults to `false`</dd>
</dl>

## Methods

<dl>
<dt><code>isValid(): boolean</code></dt>
<dd>Alias of `verifyCheckDigit()`</dd>
<dt><code>isIsbn13(options?: isOption): boolean</code></dt>
<dd>Whether it is a 13-digit ISBN</dd>
<dt><code>isIsbn10(options?: isOption): boolean</code></dt>
<dd>Whether it is a 10-digit ISBN</dd>
<dt><code>verifyFormat(): boolean</code></dt>
<dd>Verify format (do not verify check digit)</dd>
<dt><code>verifyCheckDigit(): boolean</code></dt>
<dd>Verify format including check digit (not necessarily applicable publication)</dd>
</dl>

### Arguments of `isIsbn13()` and `isIsbn10()` method

```TypeScript
interface isOption {
	check_digit?: boolean; // Verify format including check digit
}
```

\* `isIsbnXX({ check_digit: true })` has the same effect as `isIsbnXX() && isValid()`.
