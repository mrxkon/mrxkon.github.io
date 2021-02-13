---
layout: default
title: PHP Data Types
permalink: /tutorials/php-basics/php-data-types/
description: Now it&#039;s a good time to talk a bit about the other PHP Data Types that exist!
body_class: php-data-types
---
We previously covered [PHP Strings]({{ site.site_url }}/php-basics/php-strings/). Now it's a good time to talk a bit about the other PHP Data Types that exist!

You will be using all of them, so it's good to know about them as well before journeying further.

## PHP Data Types TOC

- [Null](#null).
- [Boolean](#boolean).
- [Integer](#integer).
- [Float](#float).
- [Array](#array).
- [Object](#object).
- [Strings]({{ site.site_url }}/php-basics/php-strings/).

## Null

Null means nothing. Seriously, it means that there is no value at all, don't confuse this with `0` or `false` or `''` (empty string) or any other seemingly "none" value that might exist. It's actually…nothing.

```php
<?php

// $nickname is a string.
$nickname = 'xkon';

// But now we null it.
$nickname = null;

/**
 * At this point $nickname is
 * completely empty.
 */
var_dump( $nickname );
```

## Boolean

A boolean can only be either `true` or `false`.

```php
<?php

// The red pill is truth.
$red_pill = true;

var_dump( $red_pill );

// But the blue pill is a lie.
$blue_pill = false;

var_dump( $blue_pill );
```

## Integer

Integers are numbers either positive or negative but whole. By saying whole it means that they can be like `6`, `-6`, `20`, `-23` etc, without fractions.

You can assign integers as decimal, hexadecimal, octal & binary.

```php
<?php

// Year 2019.

// Decimal.
$year = 2019;

var_dump( $year );

// Hexadecimal.
$year = 0x7E3;

var_dump( $year );

// Octal.
$year = 03743;

var_dump( $year );

// Binary.
$year = 0b11111100011;

var_dump( $year );
```

## Float

Floats are numbers but they do have a fractional part.

```php
<?php

$a_slice_of_pi = 3.14;

var_dump( $a_slice_of_pi );

$a_slice_of_pi = 3.14159265;

var_dump( $a_slice_of_pi );

$a_slice_of_pi = 3.1415926535898;

var_dump( $a_slice_of_pi );
```

## Array

Arrays are sets of data. To declare an array you can either use the `array()` function or wrap them in square brackets `[]`. Arrays can be indexed, associative and multidimensional.

All arrays are indexed by default, this means that each array data has an identifying index that starts from `0`. You can also manually add indexes if you like.

```php
<?php

// This is an array declared with "array()".

$books = array(
	'book 1',
	'book 2',
	'book 3',
);

var_dump( $books );

// This is an array declared with "[]".

$books = [
	'book 1',
	'book 2',
	'book 3',
];

var_dump( $books );
```

In associative arrays, we "exchange" the automated indexing with key values instead. This is useful when you want to bind specific data into key information.

Array keys can be either strings or integers. The main difference is that we define them instead of letting PHP use its automated indexing.

```php
<?php

$books = array(
	'Author_1' => 'book 1',
	'Author_2' => 'book 2',
	'Author_3' => 'book 3',
);

var_dump( $books );

$books = array(
	6 => 'book 6',
	7 => 'book 7',
	8 => 'book 8',
);

var_dump( $books );
```

Multidimensional arrays are easy to understand now! They are simply arrays of arrays.

```php
<?php

$books = array(
	'book_1' => array(
		'Name'    => 'the book 1',
		'Author'  => 'an author',
		'Credits' => array(
			'first'  => 'one',
			'second' => 'two',
			'third'  => 'three',
		),
		'Year'    => '2019',
	),
	'book_2' => array(
		'Name'    => 'the book 2',
		'Author'  => 'another author',
		'Credits' => array(
			'first'  => 'one',
			'second' => 'two',
			'third'  => 'three',
		),
		'Year'    => '2020',
	),
);

var_dump( $books );
```

## Object

Objects will be fully covered in the PHP Advanced tutorial as we'll discover Object-Oriented Programming.

But let's see an easy example!

```php
<?php

// A class is basically an object.
class House {
	public $bedrooms = 2;

	public $bathrooms = 1;
}

// We first have to create the object.
$a_house = new House();

// And now we can access it.
var_dump( $a_house->bedrooms );

var_dump( $a_house->bathrooms );
```

## Extra Tips on PHP Data Types

You have to be really careful with data types as they can result in unwanted situations when trying to compare them. For this, I'll tell you about [PHP Type Casting]({{ site.site_url }}/php-basics/php-type-casting/) in a future tutorial.
