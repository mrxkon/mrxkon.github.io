---
layout: default
title: PHP Operators
permalink: /php-basics/php-operators/
description: You will be using PHP Operators to perform actions on certain values. You can use them to perform various actions within your PHP.
body_class: php-operators
---
You will be using **PHP Operators** to perform actions on certain values. You can use them to perform various actions within your PHP. Such as math, comparisons, for conditions and for assignments to name a few.

Make sure to give a good read at this last part of the [PHP Basics]({{ site.site_url }}/php-basics) tutorials as there are plenty of operators to remember. You can always come back here though for a quick review if needed!

## PHP Operators TOC
- [Assignment](#assignment).
- [Arithmetic](#arithmetic).
- [Logical](#logical).
- [Comparison](#comparison).
- [Incrementing & Decrementing](#incremeting--decrementing).
- [String](#string).
- [Array](#array).
- [Spaceship](#spaceship).
- [Null Coalescing](#null-coalescing).
- [Ternary](#ternary).

## Assignment

Operator|Syntax|Description
---|---|---
`=`|`$a = $b`|$a gets set to the value of $b (Equals)
`+=`|`$a += $b`|$a gets set to $a + $b (Addition)
`-=`|`$a -= $b`|$a gets set to $a - $b (Subtraction)
`*=`|`$a *= $b`|$a gets set to $a * $b (Multiplication)
`/=`|`$a /= $b`|$a gets set to $a / $b (Division)
`%=`|`$a %= $b`|$a gets set to $a % $b (Modulus)
`**=`|`$a **= $b`|$a gets set to $a ** $b (Exponentiation)

## Arithmetic

Operator|Syntax|Description
---|---|---
`+`|`$a + $b`|Sum of $a and $b
`-`|`$a - $b`|Difference of $a and $b
`*`|`$a * $b`|Product of $a and $b
`/`|`$a / $b`|Quotient of $a and $b
`%`|`$a % $b`|Remainder of $a / $b
`**`|`$a ** $b`|Result of raising $a to the $b‘th power

## Logical

Operator|Syntax|Description
---|---|---
`and`|`$a and $b`|True if both $a and $b are true
`&&`|`$a && $b`|True if both $a and $b are true
`or`|`$a or $b`|True if either $a or $b is true
`||`|`$a || $b`|True if either $a or $b is true
`xor`|`$a xor $b`|True if either $a or $b is true, but not both
`!`|`!$a`|True if $a is not true

## Comparison

Operator|Syntax|Description
---|---|---
`==`|`$a == $b`|True if values of $a and $b are equal
`===`|`$a === $b`|True if both values and data types of $a and $b are equal
`!=`|`$a != $b`|True if $a is not equal to $b
`<>`|`$a <> $b`|True if $a is not equal to $b
`!==`|`$a !== $b`|True if $a is not equal to $b or they are not in the same data type
`>`|`$a > $b`|True if $a is greater than $b
`<`|`$a < $b`|True if $a is less than $b
`>=`|`$a >= $b`|True if $a is greater than or equal to $b
`<=`|`$a <= $b`|True if $a is less than or equal to $b

## Incrementing & Decrementing

Operator|Syntax|Description
---|---|---
`++`|`++$a`|Increments $a by one, then returns $a
`++`|`$a++`|Returns $a, then increments $a by one.
`--`|`--$a`|Decrements $a by one, then returns $a
`--`|`$a--`|Returns $a, then decrements $a by one.

## String

Operator|Syntax|Description
---|---|---
`.`|`$a . $b`|Returns the concatenation of its $a and $b
`.=`|`$a .= $b`|$a gets set to $a . $b

## Array

Operator|Syntax|Description
---|---|---
`+`|`$a + $b`|Returns the union of $a and $b arrays.
`+=`|`$a += $b`|$a gets set to $a + $b
`==`|`$a == $b`|True if $a and $b has equal key/value pairs
`===`|`$a === $b`|True if $a and $b has equal key/value pairs in the same order and of same data type.
`!=`|`$a != $b`|True if $a and $b are not equal.
`<>`|`$a <> $b`|True if $a and $b are not equal.
`!==`|`$a !== $b`|True if $a and $b has different orders, different key/value pairs or values of different data types.

## Spaceship

Operator|Syntax|Description
---|---|---
`<=>`|`1 <=> 1`|Returns 0 since both sides are equal.
`<=>`|`2 <=> 1`|Returns 1 as left side is greater.
`<=>`|`1 <=> 2`|Returns -1 as right side is greater.

The spaceship operator was added since PHP 7. You can compare [integers]({{ site.site_url }}/php-basics/php-data-types/#integer), [floats]({{ site.site_url }}/php-basics/php-data-types/#float) or [strings]({{ site.site_url }}/php-basics/php-strings).

## Null Coalescing


Operator|Syntax|Description
---|---|---
`??`|`$a ?? 1`|Returns 1 if $a was null.

The null coalescing operator was introduced since PHP 7. It's basically like an `if` [conditional]({{ site.site_url }}/php-basics/php-conditionals) but it only does one thing.

If the variable checked is null, it will assign it the new value.

```php
<?php

/**
 * If the $name is null
 * Echo 'Konstantinos'
 */

$name = null;

echo $name ?? 'Konstantinos';

/**
 * A better example with multiple nulls.
 *
 * This would output 5.
 *
 * $a is null so $b is assigned.
 * $b is null so $c is assigned.
 * $c has a value so that is echoed.
 * $d is not importatnt as we already have a value.
 *
 */

echo '<br>';

$a = null;
$b = null;
$c = 5;
$d = 10;

echo $a ?? $b ?? $c ?? $d;
```

## Ternary

Operator|Syntax|Description
---|---|---
`?:`|`$a ?: 1`|Returns 1 if $a was null.

The ternary operator is like a short `if` [conditional]({{ site.site_url }}/php-basics/php-conditionals) as well.

Its full [syntax]({{ site.site_url }}/php-basics/php-syntax) is like this to understand it a bit better.

`(condition) ? ( // code if true ) : ( // code if false )`

Since PHP 5.3, you can omit the true expression making it even easier to use.

Note that even though you can nest multiple ternary operators similar to the conditional if statements I wouldn’t recommend it as it would be really hard to read.

```php
<?php

/**
 * If the number is 1
 * echo "The number is 1."
 * else
 * echo "There is no number!"
 */

$number = rand( 0, 1 );

echo ( 1 === $number ) ? 'The number is 1.' : 'There is no number!';

/**
 * If you only like to echo $number on true
 * this could be the shorter version.
 */

echo '<br>Shorter version: ';

echo ( 1 === $number ) ?: 'There is no number!';
```

## Extra Tips for PHP Operators

Make sure to be comparing equal [data types]({{ site.site_url }}/php-basics/php-data-types). Comparing or doing math etc on strings vs numbers, for example, will be returning wrong results, if not errors.
