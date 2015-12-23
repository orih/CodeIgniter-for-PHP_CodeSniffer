# CodeIgniter-for-PHP_CodeSniffer

Provides sniffs for [PHP_CodeSniffer 1.3.0 and above](http://www.squizlabs.com/php-codesniffer) to check [CodeIgniter coding standard](http://ellislab.com/codeigniter/user-guide/general/styleguide.html).

## A bit of story

### PHP_CodeSniffer

[PHP_CodeSniffer](http://www.squizlabs.com/php-codesniffer) is a PHP5 script that tokenises and "sniffs" PHP, JavaScript and CSS files to detect violations of a defined coding standard.

It is an essential development tool that ensures your code remains clean and consistent. It can also help prevent some common semantic errors made by developers.

By default sniffs for a few coding convetions are provided like PEAR, Zend, PHPCS and Squiz. **CodeIgniter-for-PHP_CodeSniffer** is aimed at adding support for CodeIgniter coding convention.

### CodeIgniter coding standard

[CodeIgniter](http://codeigniter.com/) is a powerful PHP framework with a very small footprint, built for PHP coders who need a simple and elegant toolkit to create full-featured web applications.

CodeIgniter is developed by EllisLab. The compagny follows some specific [coding rules](http://ellislab.com/codeigniter/user-guide/general/styleguide.html) for their developments and for CodeIgniter especially.

Based on PHP_CodeSniffer **CodeIgniter-for-PHP_CodeSniffer** helps to validate most of the rules in CodeIgniter coding standard.

## Installation

Add following into your application's composer.json

```
{
...
    "repositories": [
        {
        "type": "git",
        "url": "https://github.com/orih/CodeIgniter-for-PHP_CodeSniffer.git"
        }
    ]
...
}
```

and just type this command at a place which your composer.json exists.

```
$ composer require orih/CodeIgniter-for-PHP_CodeSniffer:dev-master
```

And then configure PHP_CodeSniffer to use CodeIgniter-for-PHP_CodeSniffer.

```
$ ./vendor/bin/phpcs --configure-set installed_paths $(pwd)/vendor/orih/CodeIgniter-for-PHP_CodeSniffer/
```

Note that `phpcs` and `vendor` directory locations are depend on your composer comfiguration.

And run

```
$ ./vendor/bin/phpcs --standard=CodeIgniter ./application
```

If you don't want to use `config-set` option ahead of sniffing, you can specify it like following wihtout use `config-set`

```
$ ./vendor/bin/phpcs --standard=$(pwd)/vendor/orih/CodeIgniter-for-PHP_CodeSniffer/CodeIgniter ./application
```