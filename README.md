# PHPStan include path testing

I'm trying to figure out how to set `include_path` when running PHPStan,
so that PHPStan recognizes functions `require`d from files in `includes/`.

Here's what I get in my minimal testing:

## Using `php.ini`

```
➜ ./phpstan ini
Using php.ini to set include_path
Note: Using configuration file /app/phpstan.neon.
 1/1 [▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓] 100%

 ------ ---------------------------------------------------------------------
  Line   foo.php
 ------ ---------------------------------------------------------------------
  5      Function bar not found.
         💡 Learn more at https://phpstan.org/user-guide/discovering-symbols
 ------ ---------------------------------------------------------------------


 [ERROR] Found 1 error
```

## Using `--autoload-file` (or `bootstrapFiles` in config)

```
➜ ./phpstan
Using bootstrap file to set include_path
Note: Using configuration file /app/phpstan.neon.
 1/1 [▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓] 100%

 ------ ---------------------------------------------------------------------
  Line   foo.php
 ------ ---------------------------------------------------------------------
  5      Function bar not found.
         💡 Learn more at https://phpstan.org/user-guide/discovering-symbols
 ------ ---------------------------------------------------------------------


 [ERROR] Found 1 error
```
