    [![Latest Stable Version](https://img.shields.io/packagist/v/loophp/tin.svg?style=flat-square)](https://packagist.org/packages/loophp/tin)
 [![GitHub stars](https://img.shields.io/github/stars/loophp/tin.svg?style=flat-square)](https://packagist.org/packages/loophp/tin)
 [![Total Downloads](https://img.shields.io/packagist/dt/loophp/tin.svg?style=flat-square)](https://packagist.org/packages/loophp/tin)
 [![GitHub Workflow Status](https://img.shields.io/github/workflow/status/loophp/tin/Continuous%20Integration?style=flat-square)](https://github.com/loophp/tin/actions)
 [![Scrutinizer code quality](https://img.shields.io/scrutinizer/quality/g/loophp/tin/master.svg?style=flat-square)](https://scrutinizer-ci.com/g/loophp/tin/?branch=master)
 [![Type Coverage](https://shepherd.dev/github/loophp/tin/coverage.svg)](https://shepherd.dev/github/loophp/tin)
 [![Code Coverage](https://img.shields.io/scrutinizer/coverage/g/loophp/tin/master.svg?style=flat-square)](https://scrutinizer-ci.com/g/loophp/tin/?branch=master)
 [![License](https://img.shields.io/packagist/l/loophp/tin.svg?style=flat-square)](https://packagist.org/packages/loophp/tin)
 
# Taxpayer Identification Number (TIN) Validator

## Description

A library to validate TIN numbers for individuals. This is based on a Java
library, this is why the code does not reflect best practices in php (yet).

Supported countries:
* Austria (AT)
* Belgium (BE)
* Bulgaria (BG)
* Croatia (HR)
* Cyprus (CY)
* Czech Republic (CZ)
* Denmark (DK)
* Estonia (EE)
* Finland (FI)
* France (FR)
* Germany (DE)
* Greece (GR) - only size
* Hungary (HU)
* Ireland (IE)
* Italy (IT)
* Latvia (LV) - no check digit
* Lithuania	(LT)
* Luxembourg (LU)
* Malta (MT) - no check digit
* Netherlands (NL)
* Poland (PL)
* Portugal (PT)
* Romania (RO) - no check digit
* Slovakia (SK) - only structure
* Slovenia (SI)
* Spain (ES)
* Sweden (SE)
* United Kingdom (UK) - only structure

If your country is not there, feel free to open an issue with your country code,
and a link to the specification. Ideally, you can provide a pull request with
the algorithm and the tests.

## Requirements

* PHP >= 7.1

## Usage & API

To simply check the validity of a TIN number:

```php
<?php

include __DIR__ . '/vendor/autoload.php';

use loophp\Tin\TIN;

$bool = TIN::fromSlug('be71102512345')->isValid();
```

If you want to get the reason why a number is invalid, you can use

```php
<?php

include __DIR__ . '/vendor/autoload.php';

use loophp\Tin\TIN;
use loophp\Tin\Exception\TINException;

try {
    TIN::fromSlug('be71102512345')->check();
} catch (TINException $e) {
    // do something with the exception.
}
```

## Installation

```composer require loophp/tin```

## Code quality, tests and benchmarks

Every time changes are introduced into the library, [Github](https://github.com/loophp/tin/actions) run the tests and the benchmarks.

The library has tests written with [PHPSpec](http://www.phpspec.net/).
Feel free to check them out in the `spec` directory. Run `composer phpspec` to trigger the tests.

Before each commit some inspections are executed with [GrumPHP](https://github.com/phpro/grumphp), run `./vendor/bin/grumphp run` to check manually.

[PHPInfection](https://github.com/infection/infection) is used to ensure that your code is properly tested, run `composer infection` to test your code.

## Links

* [`European Commission TIN service`](https://ec.europa.eu/taxation_customs/tin/)
* [`TIN Algorithms - Public - Functional Specification`](https://ec.europa.eu/taxation_customs/tin/specs/FS-TIN%20Algorithms-Public.docx)
* [`Taxpayer Identification Number`](https://en.wikipedia.org/wiki/Taxpayer_Identification_Number)

## Authors
* [Thomas Portelange](https://github.com/lekoala)
* [Pol Dellaiera](https://github.com/loophp)

## Contributing

Feel free to contribute to this library by sending Github pull requests. I'm quite reactive :-)
