---
id: mining
title: Mining API
sidebar_label: Bytom.Mining.API
---

## is-mining

Returns the mining status.

#### Parameters

none

#### Returns


- `Boolean` - *is_mining*, whether the node is mining.

#### Example
```php
$client = BytomClient::isMining();
console_($client);
```
```js
// Result
{
  "is_mining": true
}
```

## set-mining

Start up node mining.

#### Parameters

- `Boolean` - *is_mining*, whether the node is mining.

#### Example
```php
$client = BytomClient::setMining();
console_($client);
```
```js
// Result
//none
```