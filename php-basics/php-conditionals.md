---
layout: default
title: PHP Conditionals
permalink: /php-basics/php-conditionals/
description: PHP Conditionals are used to run a block of code on different conditions. It&#039;s similar to what we&#039;ve seen on PHP Loops but this is more of a one-time thing.
body_class: php-conditionals
---
You will be using PHP Conditionals to run a block of code on different conditions. You already saw something similar while reading about [PHP Loops]({{ site.site_url }}/php-basics/php-loops/). This is more of a one-time thing though, as "if this is the case then do this". It's that simple.

## PHP Conditionals TOC

- [if](#if).
- [if-else](#if-else).
- [if-elseif-else](#if-elseif-else).
- [switch](#switch).

## If

The `if` conditional will run the block of code that exists inside the curly brackets only if the condition within the parenthesis is true.

The `if` conditional [syntax]({{ site.site_url }}/php-basics/php-syntax/).

`if ( condition ) { // code }`

```php

 * The Ace of Spades.
 */
$ace = 'spades';

if ( 'spades' === $ace ) {
	$lyrics = <<<'LYRICS'
If you like to gamble, I tell you I'm your man
You win some, lose some, all the same to me

The pleasure is to play, makes no difference what you say
I don't share your greed, the only card I need is the Ace of Spades

The Ace of Spades.
LYRICS;

	echo '<pre>' . $lyrics . '</pre>';
}
```

## If-Else

Since the `if` conditional will only run the block of code when the condition is met, we can use the `if-else` instead to run a different block of code when that condition is not met.

The `if-else` conditional syntax.

`if ( condition ) { // code } else { // code }`

```php
<?php

/**
 * If the condition is true
 * echo something.
 * Else
 * echo something else.
 *
 * This would output as an example:
 * Current date: 09:09:52 am
 * Ante meridiem.
 */
$date = date( 'a' );

echo 'Current date: ' . date( 'h:i:s a' ) . '<br>';

if ( 'am' === $date ) {
	echo 'Ante meridiem.';
} else {
	echo 'Post meridiem.';
}
```

## If-Elseif-Else

Sometimes you will need to take the conditional some steps further. You can always use as many `elseif` statements as you like to extend the conditional and run different blocks of code.

The `if-esleif-else` conditional syntax.

`if ( condition ) { // code } elseif { // code } else { // code }`

```php
<?php

/**
 * If the condition is true
 * do something.
 * Elseif the new condition is true
 * do something else.
 * Elseif the new condition is true
 * do something else.
 * Else if none of the conditions are true
 * do something else.
 *
 * This would output as an example:
 * The current day is the 23rd in the 4th quarter of the month.
 */

$current_day = date( 'j' );
$ordinal_day = date( 'jS' );

echo 'The current day is the ' . $ordinal_day . ' ';

if ( $current_day >= 21 ) {
	$quarter = '4th';
} elseif ( $current_day >= 14 ) {
	$quarter = '3rd';
} elseif ( $current_day >= 7 ) {
	$quarter = '2nd';
} else {
	$quarter = '1st';
}

echo 'in the ' . $quarter . ' quarter of the month.';
```

## Switch

If you want to compare the same expression instead of using the `if-elseif-else `conditional you can also use the switch. In my opinion `switch` is way more readable, especially when the condition can be met on many occasions. It is the syntax itself that makes it easier to read.

The `switch` conditional syntax.

`switch ( var ) { case var: // code; break; }`

In switch we use `break;` on every `case` to get out of the `switch` since the condition has been met. We can also use the `default:` case or omit it if we don't want to do anything similar to a final `else`.

I'll add an easy example to see the difference but imagine having ten plus different `cases`.

```php
<?php

/**
 * With an if else conditional
 * you could do it like this.
 *
 * You would get an output depending
 * on the condition.
 */

$batch = rand( 0, 3 );

if ( 1 === $batch ) {
	echo 'One batch...';
} elseif ( 2 === $batch ) {
	echo 'Two batch...';
} elseif ( 3 === $batch ) {
	echo 'One batch, Two batch.<br>Penny and Dime...';
} else {
	echo 'The Punisher.';
}


echo '<br><br>Now the switch:<br><br>';


/**
 * This is the same but
 * with the switch conditional.
 */

$batch = rand( 0, 3 );

switch ( $batch ) {
	case 1:
		echo 'One batch...';
		break;
	case 2:
		echo 'Two batch...';
		break;
	case 3:
		echo 'One batch, Two batch.<br>Penny and Dime...';
		break;
	default:
		echo 'The Punisher.';
		break;
}
```

## Extra Tips on PHP Conditionals

If all the `>=`, `===` and other symbols in conditions that you see here are confusing, they are called [PHP Operators]({{ site.site_url }}/php-basics/php-operators/) and we will check those on an upcoming tutorial!

For any of the mentioned cases of `if` conditionals, it's good to know that you can also nest them together. You can use a mixture of them as you see fit for your code.

```php
<?php

/**
 * If its AM this would output:
 * The current day is the 23rd in the 4th quarter of the month.
 *
 * If its PM this would output:
 * Sorry, this only works on AM.
 */

$current_day = date( 'j' );
$ordinal_day = date( 'jS' );
$meridiem    = date( 'a' );

if ( 'am' === $meridiem ) {
	if ( $current_day >= 21 ) {
		$quarter = '4th';
	} elseif ( $current_day >= 14 ) {
		$quarter = '3rd';
	} elseif ( $current_day >= 7 ) {
		$quarter = '2nd';
	} else {
		$quarter = '1st';
	}

	echo 'The current day is the ' . $ordinal_day . 'in the ' . $quarter . ' quarter of the month.';
} else {
	echo 'Sorry, this only works on AM.';
}
```
