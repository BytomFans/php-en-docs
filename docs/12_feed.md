---
id: feed
title: Feed API
sidebar_label: Bytom.Feed.API
---

## create-transaction-feed

Create transaction feed.

#### Parameters

- `String` - *alias*, name of the transaction feed.
- `String` - *filter*, filter of the transaction feed.

#### Returns

none if the transaction feed is created success.

#### Example
```php
$client = BytomClient::createTransactionFeed($alias, $filter);
console_($client);
```
```js
// Result
//none
```

## get-transaction-feed

Query detail transaction feed by name.

#### Parameters

`Object`:

- `String` - *alias*, name of the transaction feed.

#### Returns

`Object`:

- `String` - *id*, id of the transaction feed.

- `String` - *alias*, name of the transaction feed.

- `String` - *filter*, filter of the transaction feed.

- `Object` - *param*, param of the transaction feed.
  - `String` - *assetid*, 资产id.
  - `Integer` - *lowerlimit*, the lower limit of asset amount.
  - `Integer` - *upperlimit*, the upper limit of asset amount.
  - `String` - *transtype*, type of transaction.

#### Example

list the available txfeed by alias:
```php
$client = BytomClient::getTransactionFeed($alias);
console_($client);
```
```js
// Result
{
  "alias": "test1",
  "filter": "asset_id='84778a666fe453cf73b2e8c783dbc9e04bc4fd7cbb4f50caeaee99cf9967ebed' AND amount_lower_limit = 50 AND amount_upper_limit = 100",
  "param": {}
}
```

## list-transaction-feeds

Returns the list of all available transaction feeds.

#### Parameters

none

#### Returns

- `Array of Object` , the transaction feeds.

  - `Object` :

    - `String` - *id*, id of the transaction feed.

    - `String` - *alias*, name of the transaction feed.

    - `String` - *filter*, filter of the transaction feed.

    - ` Object` - *param* , param of the transaction feed.
      - `String` - *assetid*, asset id.
      - `Integer` - *lowerlimit*, the lower limit of asset amount.
      - `Integer` - *upperlimit*, the upper limit of asset amount.
      - `String` - *transtype*, type of transaction.

#### Example

list all the available txfeed:
```php
$client = BytomClient::listTransactionFeeds();
console_($client);
```
```js
// Result
[
  {
    "alias": "test1",
    "filter": "asset_id='84778a666fe453cf73b2e8c783dbc9e04bc4fd7cbb4f50caeaee99cf9967ebed' AND amount_lower_limit = 50 AND amount_upper_limit = 100",
    "param": {}
  },
  {
    "alias": "test2",
    "filter": "asset_id='cee6a588cc3fc280749021ef42d5209952a1e6feceada4e69dd8a424ad22b199' AND amount_lower_limit = 30 AND amount_upper_limit = 100",
    "param": {}
  }
]
```

## delete-transaction-feed

Delete transaction feed by name.

#### Parameters

- `String` - *alias*, name of the transaction feed.

#### Returns

none if the transaction feed is deleted success.

#### Example
```php
$client = BytomClient::deleteTransactionFeed($alias);
console_($client);
```
```js
// Result
//none
```

## update-transaction-feed

Update transaction feed.

#### Parameters

- `String` - *alias*, name of the transaction feed.
- `String` - *filter*, filter of the transaction feed.

#### Returns

none if the transaction feed is updated success.

#### Example

deleted when the txfeed exists, and create it with alias and filter:
```php
$client = BytomClient::updateTransactionFeed($alias, $filter);
console_($client);
```
```js
// Result
//none
```