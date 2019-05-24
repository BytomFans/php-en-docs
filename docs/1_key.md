---
id: key
title: Key API
sidebar_label: Bytom.Key.API
---

## create-key

It is to create private key essentially, returns the information of key. The private key is encrypted in the file and not visible to the user.

#### Parameters

- `String` - *alias*, name of the key.
- `String` - *password*, password of the key.

#### Returns

- `String` - *alias*, name of the key.

- `String` - *xpub*, root pubkey of the key.

- `String` - *file*, path to the file of key.
#### Example
```php
$alias = 'alice';
$pwd = '123456';
$client = BytomClient::createKey($alias, $password); 
console_($client);
```
```json
// Result
{
  "alias": "alice",
  "xpub": "a7dae957c2d35b42efe7e6871cf5a75ebd2a0d0e51caffe767db42d3e6d69dbe211d1ca492ecf05908fe6fa625ad61b3253375ea744c9442dd5551613ba50aea",
  "file": "/Path/To/Library/Bytom/keystore/UTC--2018-04-22T06-30-27.609315219Z--0e34293c-8856-4f5f-b934-37456a3820fa"
}
```
## list-keys

Returns the list of all available keys.

#### Parameters

none

#### Returns

- `Array of Object` , keys owned by the client.
  - `object` :
    - `String`  - *alias*, name of the key.
    - `String` - *xpub*, pubkey of the key.
#### Example
```php
$client = BytomClient::listKeys();
console_($client);
```
```json
// Result
[
  {
    "alias": "alice",
    "xpub": "a7dae957c2d35b42efe7e6871cf5a75ebd2a0d0e51caffe767db42d3e6d69dbe211d1ca492ecf05908fe6fa625ad61b3253375ea744c9442dd5551613ba50aea",
    "file": "/Path/To/Library/Bytom/keystore/UTC--2018-04-21T02-35-15.035935116Z--4f2b8bd7-0576-4b82-8941-6cc6da05efe3"
  },
  {
    "alias": "bob",
    "xpub": "d30a810e88532f73816b7b5007d413cbd21e526ae9159023e5262511893adc1526b8eacd691b27c080201d7d79336a4f3d2cb4c167d997821cad445765916254",
    "file": "/Path/To/Library/Bytom/keystore/UTC--2018-04-22T06-30-27.609315219Z--0e34293c-8856-4f5f-b934-37456a3820fa"
  }
]
```

## delete-key
Delete existed key, please make sure that there is no balance in the related accounts.
#### Parameters
- `String` - *xpub*, pubkey of the key.
- `String` - *password*, password of the key.
#### Returns
none if the key is deleted successfully.
#### Example
```php
$res = BytomClient::deleteKey($xpub, $password);
$this->assertEquals(200, $res->getHTTPStatus());
$client = $this->assertTrue($res->isSucceeded());
console_($client)
```
```json
// Result
// none
```
##  reset-key-password

Reset key password.

#### Parameters

- `String` - *xpub*, pubkey of the key.
- `String` - *old_password*, old password of the key.
- `String` - *new_password*, new password of the key.

#### Returns

- `Boolean` - *changed*, result of reset key password, true is reset successfully, otherwise is false.

#### Example
```php
$res = BytomClient::resetKeyPassword($xpub, $old_password, $new_password);
$this->assertEquals(200, $res->getHTTPStatus());
$client = $this->assertTrue($res->isSucceeded());
console_($client)
```
```json
// Result
{
  "changed": true
}
```