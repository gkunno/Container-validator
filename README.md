# Cargo container validator

With the Cargo container validator you can check that a container has a valid ISO 6346 code, you can also calculate container check digits, get the cargo container owners code, group code and create new cargo container check digits.

This is a fork from a piece of code (MIT licensed) I found on the web. I have modified some parts, and made the whole thing work with [Composer](http://getcomposer.org/)

*Credits shall go to the orginal author.*

## Install

Install with composer, or clone the repo to into your project.

## Documentation

Validate container ISO codes (TEXU3070079 is valid)

```php
$validator = new Gkunno\Validator;
$validator->isValid('TEXU3070079')); // bool(true) if valid
```

To get the diffrent segments from the code you can do

```php
$validator = new Gkunno\Validator;
$container = $validator->validate('TEXU3070079');
print_r($container); // Array ( [0] => TEXU3070079 [1] => TEX [2] => U [3] => 307007 [4] => 9 )

```
Where:

```php
// [0] = The code being validated
// [1] = The containers ownercode
// [2] = The containers group code
// [3] = The containers registration digit
// [4] = The containers check digit
```

How to get error messages when the containe code is invalid (TEXU3070070 is invalid)

```php
$validator = new Gkunno\Validator;
$container = $validator->validate('TEXU3070070');
$validator->isValid('TEXU3070070'); // bool(false) if invalid
print_r($validator->getErrorMessages()); // Array ( [0] => Check digit does not match
```

## License
MIT

## Credits

Salute to the original author,

[gedex.adc](http://www.google.com/gedex.web.id)


