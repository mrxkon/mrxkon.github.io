---
layout: default
title: PHP Strings
permalink: /php-basics/php-strings/
description: Eighty percent (or more) of the time, when you want to output something it will be by using PHP strings. Let&#039;s see how that works!
---
Eighty percent (or more) of the time, when you want to output something it will be by using PHP strings. Let's see how that works!

If you saw the examples on the [PHP Variables & Constants]({{ site.site_url }}/php-basics/php-variables-and-constants), most of them are strings.

You might now think "OK and what's so important I'll just put my word inside quotes ta-da!".

Sure that's the basic type of string, but there's more to it on how you are using them and with what types of quotes!

When declaring strings you have four choices. Single quoted, double quoted and doc [syntax]({{ site.site_url }}/php-basics/php-syntax) (nowdoc & heredoc).

Let's see them one by one so you can understand the differences. Trust me it's going to make sense at the end and help you a lot.

## PHP Strings TOC

- [Single Quoted](#single-quoted).
- [Double Quoted](#double-quoted).
- [Nowdoc & Heredoc](#nowdoc--heredoc).

## Single Quoted

This is the simplest form of a string and it is declared by using single quotes.

```php
<?php

$my_string = 'This is a string!';

// This would output "This is a string!".
echo $my_string;
```

But now you will ask "And what if I want to add a single quote inside a string?". Well that would break the string but you can use what we call escaping by adding an `\` in front of it.

```php
<?php

/**
 * This would produce an error.
 *
 * Because we are using an extra single quote
 * inside the string as it is.
 *
 * The string would be then ending at "Man'"
 * and since PHP won't be able to understand
 * what are the words right after it will
 * produce a syntax error.
 */
$james_brown = 'This is a Man's World!';

echo $james_brown;
```

This would work fine on the other hand. The single quote inside the string is escaped by the `\` in front.

```php
<?php

$james_brown = 'This is a Man\'s World!';

// This would output "This is a Man's World!".
echo $james_brown;
```

Now in a similar way since we are using `\` to escape in order to show a `\` character we would have to escape that also!

```php
<?php

/**
 * This would break as PHP thinks
 * that you are trying to escape the
 * single quote that holds the string.
 */
$backslash = 'Escape \';

echo $backslash;
```

<br/>

```php
<?php

// This would output "Escape \".
$backslash = 'Escape \\';

echo $backslash;
```

## Double Quoted

Double quoted strings are a totally different game. I've seen a lot of new developers using double quotes where they were not needed at all.

To put it simply, if you just want to output a string "as-is" in your code, use single quotes. If you want PHP to parse the string and adjust it, you should be using a double-quoted string.

We can still use the `\` to escape double quotes here again but let's see a few extra escape sequences that could help. We can output:

- `\\` a backslash (similar to single-quoted).
- `\”` a double-quote (similar to single-quoted).
- `\$` a dollar sign.
- `\t` a tab space.
- `\r` a carriage return.
- `\n` a line break.

You guessed it! Since PHP can parse double-quoted strings we can use the `$` sign to also output variables inside strings.

```php
<?php

$name = 'Konstantinos';

// No need for double quotes sinde this is just HTML.
echo '<pre>';

/**
 * Now we use various escaping sequences
 * so we use double quotes.
 */
echo "Hi...\n";

echo "My name is.\tHuh?\r";
echo "My name is.\tWhat?\r";
echo "My name is.\r\n";

echo "\t\tchka-chka {$name}!";

// No need for double quotes again :).
echo '</pre>';

// This would output.
Hi...
My name is.     Huh?
My name is.     What?
My name is.
                chka-chka Konstantinos!
```

Note that the variable inside the string is used with curly brackets `{}` as well. This is because we want to define where is the start and the end of the variable, to avoid extra character conflicts.

```php
<?php

$name = 'Konstantino';

// This would not work as "$names" doesn't exist.
echo "My name is $names";

/**
 * This would work but leave a space between the
 * variable and the "s".
 */
echo "My name is $name s";

/**
 * This would work as expected as we define
 * the start and end of the variable.
 */
echo "My name is {$name}s";
```

I suggest to always use curly brackets whether you want to add extra characters or not. This is just for readability and consistency.

## Nowdoc & Heredoc

Nowdoc uses single quotes and heredoc uses double quotes similar to the strings mentioned before.

In nowdoc no parsing would be made, but PHP will parse the heredoc strings.

Both nowdoc and heredoc start with `<<<` and then an identifier with single or double-quotes. You should always end their syntax with the identifier again.

```php
<?php

$nowdoc = <<<'LYRICS'
I am a world before I am a man
I was a creature before I could stand
I will remember before I forget
Before I forget that
LYRICS;

echo '<pre>' . $nowdoc . '</pre>';
```

<br/>

```php
<?php

$artist = 'Slipknot';
$song   = 'Before I Forget';

$heredoc = <<<"LYRICS"
Song: {$artist} - {$song}.

I am a world before I am a man
I was a creature before I could stand
I will remember before I forget
Before I forget that
LYRICS;

echo '<pre>' . $heredoc . '</pre>';
```

## Extra Tips on PHP Strings

In doc syntax, there's no need to escape quotes when they are typed inside the strings. This way it's much easier to output other languages as well if needed as HTML etc.
