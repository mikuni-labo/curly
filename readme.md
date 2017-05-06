# Curly

[![Latest Stable Version](https://poser.pugx.org/mikuni-labo/curly/v/stable)](https://packagist.org/packages/mikuni-labo/curly)
[![Latest Unstable Version](https://poser.pugx.org/mikuni-labo/curly/v/unstable)](https://packagist.org/packages/mikuni-labo/curly)
[![License](https://poser.pugx.org/mikuni-labo/curly/license)](https://packagist.org/packages/mikuni-labo/curly)
[![composer.lock](https://poser.pugx.org/mikuni-labo/curly/composerlock)](https://packagist.org/packages/mikuni-labo/curly)

This library is Manipulate the Curl library for PHP.

## Installation

### With Composer

```
$ composer require mikuni-labo/curly
```

```json
{
    "require": {
        "mikuni-labo/curly": "^1.0.0"
    }
}
```

## Example
```php
<?php
require 'vendor/autoload.php';

use MikuniLabo\Curly\Curly;

$ch = new Curly;

$ch->init();
$ch->setUrl('http://example.com/');// Request URL
$ch->setMethod('GET');             // Request Method
$ch->setUserPwd('auth-basic-user-id', 'auth-basic-password');// Auth Basic Credentials
$ch->setHeaderFromArray(array(     // Header
    'Content-type: application/json',
    // More any parameter...
));
$ch->setParameterFromArray(array(  // Request Parameter
    'key' => 'value',
    // More any parameter...
));
$ch->setJsonTransfer(true);
$response = $ch->exec();
$ch->close();

print_r( $response );
```
