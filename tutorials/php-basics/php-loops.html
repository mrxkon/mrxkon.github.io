---
layout: default
title: PHP Loops
permalink: /tutorials/php-basics/php-loops/
description: PHP Loops are used to run a block of code until a condition is met. You can use them as simple count mechanisms, or to loop through data.
body_class: php-loops
---
PHP Loops are used to run a block of code until a condition is met. You can use them as simple count mechanisms, or to loop through data.

## PHP Loops TOC

- [for](#for).
- [foreach](#foreach).
- [while & do-while](#while--do-while).

## For

I'd say that the `for` loop is one of the weirdest to use. But if you can understand it's basic it becomes really easy. Let's see the [syntax]({{ site.site_url }}/php-basics/php-syntax/) first.

You have to use three expressions here as a starting point, an ending point and in the middle the conditional that you are checking with.

Note that the starting & conditional are ending with an `;` character but the ending does not.

`for ( starting; conditional; ending ) { // code }`

```php
<?php

/**
 * We say that $i starts with 1.
 *
 * For each time it is less than 6.
 *
 * It should become +1 and run the code.
 *
 * This would output:
 * 1
 * 2
 * 3
 * 4
 * 5
 */

for ( $i = 1; $i < 6; $i++ ) {
	echo $i . '<br>';
}
```

Each of the three expressions can be either empty or have multiple expressions as well that you can separate with a comma.

```php
<?php

/**
 * We start with $y 20 & $z 30.
 *
 * For each time $y is less than
 * or equal to $z.
 *
 * Add 1 to $y and subtract 1 from $z.
 *
 * This would output:
 * $y 20 / $z 30
 * $y 21 / $z 29
 * $y 22 / $z 28
 * $y 23 / $z 27
 * $y 24 / $z 26
 * $y 25 / $z 25
 */

for ( $y = 20, $z = 30; $y <= $z; $y++, $z-- ) {
	echo '$y ' . $y . ' / $z ' . $z . '<br>';
}
```

For loops can also be nested to create more complex routines.

```php
<?php

/**
 * These nested for loops
 * would ouput a 10x10 square.
 */

echo '<div style="line-height:0.5">';

for ( $y = 0; $y < 10; $y++ ) {
	for ( $x = 0; $x < 10; $x++ ) {
		echo '*';
	}

	echo '<br>';
}

echo '</div>';
```

## Foreach

The `foreach` loop, as mentioned previously, can be used to loop through arrays. You can use it for any type of array, indexed, associative and multidimensional as well.

The `foreach` loop syntax.

`foreach ( $array as $key => $value ) { // code }`

Let's start with an indexed array, on this occasion we can omit the `$key`.

```php
<?php

// Let's create an array.
$books = array(
	'book 1',
	'book 2',
	'book 3',
);

/**
 * Now we can loop through it.
 *
 * This would output:
 * book 1
 * book 2
 * book 3
 */
foreach ( $books as $book ) {
	echo $book . '<br>';
}
```

Let's see an associative array and how we could now use the `$key`.

```php
<?php

// Let's create an array.
$books = array(
	'author 1' => 'book 1',
	'author 2' => 'book 2',
	'author 3' => 'book 3',
);

/**
 * Now we can loop through it.
 *
 * This would output:
 * Book 'book 1' by author 1
 * Book 'book 2' by author 2
 * Book 'book 3' by author 3
 */
foreach ( $books as $author => $book ) {
	echo "Book '{$book}' by {$author} <br>";
}
```

The multidimensional arrays will need nested foreach loops, similar to what we did with the `for` loop earlier.

```php
<?php

// Let's create an array.
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

/**
 * Now we can loop through it.
 *
 * This would output:
 * Name: the book 1
 * Author: an author
 * Credits: one, two, three
 * Year: 2019
 *
 * Name: the book 2
 * Author: another author
 * Credits: one, two, three
 * Year: 2020
 */
foreach ( $books as $book => $information ) {
	foreach ( $information as $info => $details ) {
		if ( ! is_array( $details ) ) {
			echo $info . ': ' . $details . '<br>';
		} elseif ( is_array( $details ) ) {
			echo $info . ': ' . implode( ', ', $details ) . '<br>';
		}
	}
	echo '<br>';
}
```

## While & Do-While

These two loops are very similar. Their only difference is that the `while` loop will not execute the block of code at all is the condition is already met. The `do-while` loop, on the other hand, will have to execute the code at least one time.

Let's see some examples so you can understand their difference 😊.

The `while` loop syntax.

`while ( $var < $value ) { // code }`

```php
<?php

/**
 * A "while" loop.
 *
 * This would output:
 * Counting: 1
 * Counting: 2
 * Counting: 3
 * Counting: 4
 * Counting: 5
 */
$count = 1;

while ( $count <= 5 ) {
	echo 'Counting: ' . $count . '<br>';
	$count++;
}
```

The `do-while` syntax.

`do { // code } while ( $var < $value );`

```php
<?php

/**
 * A similar "do-while" loop.
 *
 * This would output:
 * Counting: 1
 * Counting: 2
 * Counting: 3
 * Counting: 4
 * Counting: 5
 */

$count = 1;

do {
	echo 'Counting: ' . $count . '<br>';
	$count++;
} while ( $count <= 5 );
```

To easily understand the difference now let's use the same example.

```php
<?php

/**
 * $count is 0.
 *
 * The while loop exits
 * from the start so
 * it will not output anything.
 *
 */
$count = 0;

while ( $count > 0 ) {
	echo 'Counting: ' . $count . '<br>';
}

/**
 * $count is 0.
 *
 * On the "do-while" though
 * the code block runs first
 * and then the check.
 *
 * This would output:
 * Counting: 0
 */

$count = 0;

do {
	echo 'Counting: ' . $count . '<br>';
} while ( $count > 0 );
```

## Extra Tips on PHP Loops

Instead of always using random variables like `$a`, `$x` etc on `for` & `while` loops, it is better to use variable names that will make sense in your code. Unless they are not important at all to remember.