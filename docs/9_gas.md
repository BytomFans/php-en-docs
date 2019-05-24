---
id: gas
title: Gas_rate API
sidebar_label: Bytom.Gas.API
---

## gas-rate

Quary gas rate.

#### Parameters

none

#### Returns

- `Integer` - *gas_rate*, gas rate.

#### Example
```php
$client = BytomClient::gasRate();
console_($client);
```
```js
// Result
{
  "gas_rate": 1000
}
```

