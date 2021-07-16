# Václav Vaník Coding Standard

The Václav Vaník Coding Standard `VVCS` is a set of [PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer)
rules applied to my projects.

VVCS is inspired by [Doctrine Coding Standard](https://github.com/doctrine/coding-standard)
and heavily based on [Slevomat Coding Standard](https://github.com/slevomat/coding-standard).

## Installation

The recommended way to install PHP CS Fixer is to use [Composer](https://getcomposer.org/download/)
in a dedicated `composer.json` file in your project, for example in the
`tools/php-coding-standard` directory:

```bash
mkdir --parents tools/php-coding-standard
composer require --working-dir=tools/php-coding-standard vaclavvanik/coding-standard
cp tools/php-coding-standard/vendor/vaclavvanik/coding-standard/example.phpcs.xml tools/php-coding-standard/.phpcs.xml
cp tools/php-coding-standard/vendor/vaclavvanik/coding-standard/.gitignore tools/php-coding-standard/.gitignore
```

## Configuration

Example `.phpcs.xml`:

```xml
<?xml version="1.0"?>
<ruleset
        xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
        xsi:noNamespaceSchemaLocation="vendor/squizlabs/php_codesniffer/phpcs.xsd"
>
    <arg name="basepath" value="."/>
    <arg name="cache" value=".phpcs-cache"/>
    <arg name="colors"/>
    <arg name="extensions" value="php"/>
    <arg name="parallel" value="80"/>

    <!-- Show progress and rule -->
    <arg value="ps"/>

    <!-- Paths to check -->
    <file>../../src</file>
    <file>../../test</file>

    <rule ref="VaclavVanik"/>
</ruleset>
```

[Ruleset documentation](https://github.com/squizlabs/PHP_CodeSniffer/wiki/Annotated-Ruleset).

## Usage

Fix:

`./tools/php-coding-standard/vendor/bin/phpcbf --basepath=. --standard=tools/php-coding-standard/.phpcs.xml`

Check:

`./tools/php-coding-standard/vendor/bin/phpcs --basepath=. --standard=tools/php-coding-standard/.phpcs.xml`
