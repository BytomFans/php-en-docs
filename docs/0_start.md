---
id: start
title: quick start
sidebar_label: SDK环境配置
---
## Installation

There are various ways to install and use this sdk. We'll elaborate on a couple here. Note that the Bytom PHP SDK requires PHP 5.4 or newer.

### Install with Composer

1. To install the SDK with Composer, you will need to be using [Composer](http://getcomposer.org/)in your project. If you aren't using Composer yet, it's really simple! Here's how to install composer:

```bash
curl -sS https://getcomposer.org/installer | php
```
2. Then create a composer.json file in your projects root folder, containing:

```json
{
    "require": {
        "lxlxw/bytom-php-sdk" : "dev-master"
    }
}
```
3. Run "composer install" to download the SDK and set up the autoloader,and then require it from your PHP script:

```php
require './vendor/autoload.php';
```
### Install with Git
从github上clone该项目：https://github.com/lxlxw/bytom-php-sdk.git
```bash
git clone https://github.com/lxlxw/bytom-php-sdk.git
```
包含`autoload.php` 文件从而自动获取Bytom SDK中的类

```php
require 'autoload.php';
```

### Install with Composer

To install the SDK with Composer, you will need to be using [Composer](http://getcomposer.org/)
in your project.
If you aren't using Composer yet, it's really simple! Here's how to install
composer:

## Usage

### Usage examples
You should always use Composer's autoloader in your application to automatically load the your dependencies. All examples below assumes you've already included this in your file:

```php
require 'vendor/autoload.php';
use Bytom\BytomClient;
```

Here's how to send a message using the SDK:

```php
# First, instantiate the SDK Client

# Local node, default url is `127.0.0.1:9888`
$client = new BytomClient();
# Remote node
$client = new BytomClient('url', 'auth-token');

# Now, request bytom api.
$alias = 'test_name';
$pwd = '123456';
$res = $client->createKey($alias, $pwd);
$data = $res->getJSONDecodedBody();
```

### All usage examples

You find more detailed documentation at[API](1_key.md)

## Support and Feedback

If you find a bug, please submit the issue in Github directly.
[Bytom-PHP-SDK Issues](https://github.com/lxlxw/bytom-php-sdk/issues)

## Contact

- Email：<x@xwlin.com>

