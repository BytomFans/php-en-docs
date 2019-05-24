---
id: work
title: Work API
sidebar_label: Bytom.Work.API
---

## get-work

Get the proof of work.

#### Parameters

none

#### Returns

`Object`:

- `Object` - *block_header*, raw block header.
- `Object` - *seed*, seed.


#### Example
```php
$client = BytomClient::getWork();
console_($client);
```
```js
// Result
{
  "block_header": "0101870103f2c7495164c8f3af43697e81faa21dcb2d60aa5e10ce4f233491e62420742fbeadfcd50540bef2670a5fade2e58ad4955e2375a04ad1e4cb9c104faddab43f4a79e35be253c9c377e5192668bc0a367e4a4764f11e7c725ecced1d7b6a492974fab1b6d5bc00ffffff838080808020",
  "seed": "702bef3f1707577fd0d75b6359a2919fa216487fe306771e27710acbaa9164ce"
}
```


## submit-work

Submit the proof of work.

#### Parameters

- `Object` - *block_header*, raw block header.

#### Returns

true if success.

#### Example
```php
$client = BytomClient::submitWork($block_header);
console_($client);
```
```js
// Result
true / error
```