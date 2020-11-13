---
layout: default
title: PHP Syntax
permalink: /php-basics/php-syntax/
description: PHP is a programming language that is what I like to call &quot;talkative&quot; by itself so if you pay attention to its syntax it is really easy to understand.
---
PHP is what I like to call "talkative". If you pay attention to its syntax it is really easy to understand and follow.

> We call syntax the structure of statements in a computer language.

You can easily identify PHP code as it must live within the `<?php` and `?>` (opening and closing tags) as well as written in a .php file.

On the following statement example, our code is written in `<?php` and it should echo (output) a string. The `;` at the end terminates this statement and since we are only using PHP we can omit the `?>` closing tag as there’s no other language following.

```php
<?php

echo 'Welcome to the PHP Basics tutorial!';
```

I have to mention now just for general knowledge that PHP syntax is **semi case sensitive**. This means that on some occasions it cares about being case sensitive and on some others it does not. For example statements like if, while, for & functions, as well as classes, are **case insensitive** while variables are **case sensitive**.

```php
<?php

// This would output "PHPBasics".

echo 'PHP';
eChO 'Basics';
<?php

// But this would output just "PHP".

$say    = 'PHP';
$basics = 'Basics';

echo $say . $bAsIcS;
```

Even though some aspects of the language are case insensitive it is good practice to use standards in your code. Try to have consistency i.e. for [variables]({{ site.site_url }}/php-basics/php-variables-and-constants) use lowercase letters and capitalize your classes. This consistency will help you as well as the code will be easier to be read by others.

## Comments in PHP Syntax

I've always been a fan of spacious and well-commented code. It helps to easily remember why it was written and what its purpose is.

I'm not going to debate "tabs" vs "spaces". I personally use tabs, but that's up to you. What I will strongly advise is adding an empty line when it's needed and write comments as much as possible. This gives your code a more human-readable form.

Let's see the types of comments that you can use!

For single lines, you can use either `//` or `#` at the start of each line and for multi-line comments as well as "commenting out" parts of code you can start with `/*` and end with `*/`.


```php
<?php

// This is a single line comment.

# This is a single line comment as well!

/*
    This is an example of
    a multi-line comment.
*/

/**
 * This is what we call
 * a "block comment".
 */

// This will output "15" as the "+ 2" has been commented out.
$mystring = 10 /* + 2 */ + 5;

echo $mystring;
```

## Extra Tips

WordPress community has it’s own [PHP Coding Standards](https://developer.wordpress.org/coding-standards/wordpress-coding-standards/php/){:target="_blank"}{:rel="noopener noreferrer"} that you can apply to your syntax.

You can set up your coding environment with extra helping tools you can also use [PHP Code Sniffer](https://github.com/squizlabs/PHP_CodeSniffer){:target="_blank"}{:rel="noopener noreferrer"}. [WordPress Coding Standards](https://github.com/WordPress/WordPress-Coding-Standards){:target="_blank"}{:rel="noopener noreferrer"} are additional rules for PHPCS to automatically find issues with your syntax.