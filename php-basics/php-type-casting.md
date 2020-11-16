---
layout: default
title: PHP Type Casting
permalink: /php-basics/php-type-casting/
description: PHP Type Casting comes along with PHP Data Types. But as I&#039;ve mentioned comparing data types or using them wrongly might result in errors.
---
PHP Type Casting comes along with [PHP Data Types]({{ site.site_url }}/php-basics/php-data-types). But as I've mentioned comparing data types or using them wrongly might result in errors or unwanted behavior in your code.

You can cast either explicitly (manually) or leave it as implicit (automated).

## PHP Type Casting TOC

- [Implicit](#implicit).
- [Explicit](#explicit).

## Implicit

PHP is smart enough to automate this on its data. This means that it will change the type of variables according to what they actually hold as data.

```php
<?php

// This is an integer.
$ten = 10;

// This is another integer.
$five = 5;

// We do the math.
$math = $ten / $five;

/**
 * This would result on an integer again.
 *
 * 10 / 5 = 2
 */
var_dump( $math );

// We do the math again.
$math = $five / $ten;

/**
 * This would result on a float this time.
 *
 * 5 / 10 = 0.5
 */

var_dump( $math );
```

## Explicit

By explicitly [casting](https://www.php.net/manual/en/internals2.opcodes.cast.php){:target="_blank"}{:rel="noopener noreferrer"} a type you are basically “forcing” PHP to go your way. This means that you can change the data type at any point.

Note again that if not done correctly you might result in unwanted behavior. See the example and you'll understand why.

To manually cast a data type we use its type in parenthesis right before the value.

- (string)
- (int)
- (float)
- (bool)
- (array)
- (object)

Let's see some examples so you can understand how data types can change the outcome of your code.

```php
<?php

/**
 * (string) example.
 */

// This is an integer.
$ten = 10;

// Now we cast it as a string.
$cast = (string) $ten;

var_dump( $cast );
```

<br/>

```php
<?php

/**
 * (int) example.
 */

// This is a string.
$ten = '10';

// Now we cast it as an integer.
$cast = (int) $ten;

var_dump( $cast );

// This is a float.
$price = 12.45;

// Now we cast it as an integer.
$cast = (int) $price;

/**
 * Note that since integers do
 * not have decimals the output
 * will be "12" as it was converted.
 */

var_dump( $cast );
```

<br/>

```php
<?php

/**
 * (float) example.
 */

// This is an integer.
$ten = 10;

// Now we cast it as a float.
$cast = (float) $ten;

var_dump( $cast );

// This is a string.
$price = '12.45';

// Now we cast it as a float.
$cast = (float) $price;

/**
 * Note that since floats do
 * have decimals the value
 * will remain as is.
 */

var_dump( $cast );
```

<br/>

```php
<?php

/**
 * (bool) example.
 *
 * Booleans are either true or false.
 *
 * Depending on if there's data inside
 * a variable, the state between true
 * or false will also change.
 */

// This would be false.
$a = (bool) 0;
var_dump( $a );

// This would be true.
$b = (bool) 5;
var_dump( $b );

// This would be false.
$c = (bool) '';
var_dump( $c );

// This would be true.
$d = (bool) 'something';
var_dump( $d );

// This would be false.
$e = (bool) array();
var_dump( $e );

// This would be true.
$f = (bool) array( 10, 20, 30 );
var_dump( $f );

// This would be false.
$g = (bool) null;
var_dump( $g );
```

<br/>

```php
<?php

/**
 * (array) example.
 *
 * Casting to an array is useful only
 * if you want to add a starting value.
 *
 * Any value will simply be converted into
 * the first data in an indexed array.
 */

$a = (array) 10;
var_dump( $a );

$b = (array) 'xkon';
var_dump( $b );

$c = (array) true;
var_dump( $c );

$d = (array) false;
var_dump( $d );

$e = (array) 10.34;
var_dump( $e );
```

<br/>

```php
<?php

/**
 * (object) example.
 *
 * Convert an array to an object.
 */

$a = array(
	10,
	20,
	30,
);

var_dump( $a );

$b = (object) $a;

var_dump( $b );

```

## Extra Tips on PHP Type Casting

Well! Not an extra tip basically but I'm going to say again to be very very careful of the data types and cast them as needed if needed. I've seen many issues in stores especially when doing maths and this is forgotten. They end up having wrong values on their carts and that's a recipe for disaster!