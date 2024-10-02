# Introducing PHP Datatypes: A Strict and Safe Way to Handle Primitive Data Types

[![Latest Version on Packagist](https://img.shields.io/packagist/v/nejcc/php-datatypes.svg?style=flat-square)](https://packagist.org/packages/nejcc/php-datatypes)
[![Total Downloads](https://img.shields.io/packagist/dt/nejcc/php-datatypes.svg?style=flat-square)](https://packagist.org/packages/nejcc/php-datatypes)
![GitHub Actions](https://github.com/nejcc/php-datatypes/actions/workflows/main.yml/badge.svg)

I'm excited to share my latest PHP package, PHP Datatypes. This library introduces a flexible yet strict way of handling primitive data types like integers, floats, and strings in PHP. It emphasizes type safety and precision, supporting operations for signed and unsigned integers (Int8, UInt8, etc.) and various floating-point formats (Float32, Float64, etc.).

With PHP Datatypes, you get fine-grained control over the data you handle, ensuring your operations stay within valid ranges. It's perfect for anyone looking to avoid common pitfalls like overflows, division by zero, and unexpected type juggling in PHP.

## Installation

You can install the package via composer:

```bash
composer require nejcc/php-datatypes
```

## Usage

Below are examples of how to use the basic integer and float classes in your project.


### Laravel example

```php
<?php

namespace App\Http\Controllers;

use Illuminate\Http\Request;
use Nejcc\PhpDatatypes\Integers\Unsigned\UInt8;

class TestController
{
    public UInt8 $user_id;
    public function __invoke(Request $request)
    {
        $this->user_id = uint8($request->input('user_id'));
        dd($this->user_id->getValue());
    }
}
```

PHP examples

### Integers
```php
use Nejcc\PhpDatatypes\Integers\Signed\Int8;
use Nejcc\PhpDatatypes\Integers\Unsigned\UInt8;

$int8 = new Int8(-128); // Minimum value for Int8
echo $int8->getValue(); // -128

$uint8 = new UInt8(255); // Maximum value for UInt8
echo $uint8->getValue(); // 255
```

### Floats
```php
use Nejcc\PhpDatatypes\Floats\Float32;
use Nejcc\PhpDatatypes\Floats\Float64;

$float32 = new Float32(3.14);
echo $float32->getValue(); // 3.14

$float64 = new Float64(1.7976931348623157e308); // Maximum value for Float64
echo $float64->getValue(); // 1.7976931348623157e308
```

### Arithmetic Operations
```php
use Nejcc\PhpDatatypes\Integers\Signed\Int8;

$int1 = new Int8(50);
$int2 = new Int8(30);

$result = $int1->add($int2); // Performs addition
echo $result->getValue(); // 80

```

### Testing

```bash
composer test
```

### Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information what has changed recently.

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.

### Security

If you discover any security related issues, please email nejc.cotic@gmail.com instead of using the issue tracker.

## Credits
-   [Nejc Cotic](https://github.com/nejcc)

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.

## PHP Package Boilerplate

This package was generated using the [PHP Package Boilerplate](https://laravelpackageboilerplate.com) by [Beyond Code](http://beyondco.de/).
