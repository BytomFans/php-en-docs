---
id: decode_program
title: Decode_program API
sidebar_label: Bytom.Decode_program.API
---

## decode-program

Decode program. 

#### Parameters

- `String` - *program*, program for account.

#### Returns

`Object`:

- `String` - *instructions*, instructions and data for program.

#### Example
```php
$client = BytomClient::decodeRawTransaction($raw_transaction);
console_($client);
```
```js
// Result
{
  "instructions": "DUP \nHASH160 \nDATA_20 a86c83ee12e6d790fb388345cc2e2b87056a0773\nEQUALVERIFY \nTXSIGHASH \nSWAP \nCHECKSIG \n"
}
```