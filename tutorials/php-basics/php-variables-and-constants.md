---
layout: default
title: PHP Variables &amp; Constants
permalink: /tutorials/php-basics/php-variables-and-constants/
description: PHP variables &amp; constants are used for storing information that we can retrieve later on in our code. The key difference is the variables data can be...
body_class: php-variables-and-constants
---
You can retrieve in your code anything that you have stored in PHP variables & constants. Variables data can be changed and constants are permanent, that's a key difference.

If you've read the [PHP Syntax]({{ site.site_url }}/php-basics/php-syntax/) article, you already know that it's always good to name your variables and constants with something that is related to your code. You will easily remember and identify them this way.

## PHP Variables & Constants TOC

- [Variables](#variables).
- [Superglobal Variables](#superglobal-variables).
- [Constants](#constants).

## Variables

All variables must start with a `$` sign and can contain only letters, numbers and underscores. The first character after the `$` cannot be a number and remember they are case sensitive!

```php
<?php

// This is correct.
$name = 'Konstantinos';

// This is correct as well.
$_last_name_ = 'Xenos';

// This is also correct!
$_middlename123 = 'debugger';

// This is not correct.
$66_route = 'get your kicks';

// This is also not correct.
$current age = 36;
```

You can declare new values since the data in a variable can be changed, but only the last one will be returned.

Don't get confused for the time being if '' is used or not. You will be able to read about [data types]({{ site.site_url }}/php-basics/php-data-types/), [type casting]({{ site.site_url }}/php-basics/php-type-casting/) and [strings]({{ site.site_url }}/php-basics/php-strings/) in future posts.

```php
<?php

// First declaration.
$myvar = 'first';

// Second declaration.
$myvar = 'second';

// This would output "second" as that's the last value that was declared.
echo $myvar;
```

Variables can have 3 scopes. They can be global, local and static. Let's see some examples in code!

```php
<?php

/**
 * Variables declared in the general area of your code
 * are global.
 *
 * As an example here the $name can be parsed directly,
 * but have to be accessed from a function either by adding
 * "global" in front of it, or by the "$GLOBALS" PHP array.
 */

$name = 'xkon';
$site = 'xkon.gr';

// This would output "xkon".
echo $name;

// This would output "xkon xkon.gr" as well.
function information() {
	global $name;

	echo $name . ' ' . $GLOBALS['site'];
}

information();

// This would be wrong though as the variable is global.
function wrong() {
	echo $name;
}

wrong();
```

<br/>

```php
<?php

/**
 * Variables declared in functions have a local scope.
 *
 * You will not be able to parse them outside
 * of the function.
 *
 * Since the variable is local, think of it as if it
 * is gettingremoved by the memory and re-declared
 * each time you are running the function.
 */

function mambo() {
	$number = '5';

	echo $number;
}

// This would output "5"
mambo();

// This would output "5" again.
mambo();

// But this wouldn't work.
echo $number;
```

<br/>

```php
<?php

/**
 * As seen on the previous example since
 * a variable declared inside a function
 * is getting "reset" each time we run the
 * function we also have the "static" variables.
 *
 * To declare them as static simply write "static"
 * infront of the variable.
 *
 * This way they are not getting reset and you
 * can dynamically alter them.
 *
 * Essentially on this example each time you run
 * mambo(), the variable will always be +3 of its
 * last value.
 */

function mambo() {
	static $number = '2';

	echo $number . '<br>';

	$number = $number + 3;
}

/**
 * This would output "2" as the echo
 * is before the + 3.
 */
mambo();

/**
 * But this would output "5" as we run
 * the function again and the variable
 * was updated.
 */
mambo();
```

## Superglobal Variables

Since we covered the variables let's also make a really brief mention at the superglobal variables. I'm mentioning this as I've already shown you one of them that is `$GLOBALS`.

- [$GLOBALS](https://www.php.net/manual/en/reserved.variables.globals.php){:target="_blank"}{:rel="noopener noreferrer"}.
- [$_GET](https://www.php.net/manual/en/reserved.variables.get.php){:target="_blank"}{:rel="noopener noreferrer"}.
- [$_POST](https://www.php.net/manual/en/reserved.variables.post.php){:target="_blank"}{:rel="noopener noreferrer"}.
- [$_COOKIE](https://www.php.net/manual/en/reserved.variables.cookies.php){:target="_blank"}{:rel="noopener noreferrer"}.
- [$_REQUEST](https://www.php.net/manual/en/reserved.variables.request.php){:target="_blank"}{:rel="noopener noreferrer"}.
- [$_SESSION](https://www.php.net/manual/en/reserved.variables.session.php){:target="_blank"}{:rel="noopener noreferrer"}.
- [$_ENV](https://www.php.net/manual/en/reserved.variables.environment.php){:target="_blank"}{:rel="noopener noreferrer"}.
- [$_FILES](https://www.php.net/manual/en/reserved.variables.files.php){:target="_blank"}{:rel="noopener noreferrer"}.
- [$_SERVER](https://www.php.net/manual/en/reserved.variables.server.php){:target="_blank"}{:rel="noopener noreferrer"}.

## Constants

Constants are a bit easier to understand and remember. They are always of global scope even if you declare them inside a function and they are case insensitive. It's better to be consistent as I've mentioned so you should declare constants with uppercase letters.

The naming convention is similar to the variables with the difference that `$` is not used. To declare a constant you need to use a PHP statement instead called `define()`.

```php
<?php

// Declaring a constant.
define( 'FIRST_CONSTANT', 'first' );

// This would output "first".
echo FIRST_CONSTANT;

/**
 * Declaring a constant is global
 * so it can be used anywhere without
 * the need of "global" or "$GLOBALS".
 */
define( 'SECOND_CONSTANT', 'second' );

function second() {
	echo SECOND_CONSTANT;
}

// This would output "second".
second();

/**
 * Even though the constant is defined inside
 * the function. When this function is run
 * the constant becomes global from that point
 * on.
 */
function third() {
	define( 'THIRD_CONSTANT', 3 );
}

third();

// This would output "3".
echo THIRD_CONSTANT;

/**
 * Since constants are permanent and can't
 * be changed. This would produce a notice
 * as it is wrong.
 *
 * The output would always return "yellow"
 * as that's the first declaration that
 * the constant had in the code.
 */
define( 'COLOR', 'yellow' );

define( 'COLOR', 'blue' );

// This would output "yellow".
echo COLOR;
```

In WordPress you will find some constants in your `wp-config.php` such as the database credentials since their values should be the same always when used in future code references.

## Extra Tips on PHP Variables & Constants

You should not use the $this variable on "general" code as it is a pseudo-variable. You can only use it to refer to an object of a method. In time I'll try to create an extra **PHP Advanced** tutorial explaining OOP ([Object-Oriented Programming](https://en.wikipedia.org/wiki/Object-oriented_programming){:target="_blank"}{:rel="noopener noreferrer"}) in PHP.
