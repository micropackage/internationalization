# Internationalization

[![BracketSpace Micropackage](https://img.shields.io/badge/BracketSpace-Micropackage-brightgreen)](https://bracketspace.com)
[![Latest Stable Version](https://poser.pugx.org/micropackage/internationalization/v/stable)](https://packagist.org/packages/micropackage/internationalization)
[![PHP from Packagist](https://img.shields.io/packagist/php-v/micropackage/internationalization.svg)](https://packagist.org/packages/micropackage/internationalization)
[![Total Downloads](https://poser.pugx.org/micropackage/internationalization/downloads)](https://packagist.org/packages/micropackage/internationalization)
[![License](https://poser.pugx.org/micropackage/internationalization/license)](https://packagist.org/packages/micropackage/internationalization)

<p align="center">
    <img src="https://bracketspace.com/extras/micropackage/micropackage-small.png" alt="Micropackage logo"/>
</p>

## 🧬 About Internationalization

The Internationalization micropackage is an unified wrapper for both `load_plugin_textdomain` and `load_theme_textdomain` functions.

It can handle both theme and plugin language packs but also any other 3rd party library, like a translated Composer package.

The language file must follow the scheme: `{textdomain}-{locale_LOCALE}.mo`.

This package is compatible with [DocHooks library](https://github.com/micropackage/dochooks).

## 💾 Installation

``` bash
composer require micropackage/internationalization
```

## 🕹 Usage

Call the action manually:

```php
use Micropackage\Internationalization\Internationalization;

add_action( 'init', [ new Internationalization( $textdomain, $full_language_dir_path ), 'load_translation' ] );
```

Using [DocHooks library](https://github.com/micropackage/dochooks):

```php
Micropackage\DocHooks\Helper::hook( new Internationalization( $textdomain, $full_language_dir_path ) );
```

Retrieving full path to the directory:

```php
$theme_language_dir  = get_template_directory() . '/languages';
$plugin_language_dir = plugin_dir_path( __FILE__ );
```

## 📦 About the Micropackage project

Micropackages - as the name suggests - are micro packages with a tiny bit of reusable code, helpful particularly in WordPress development.

The aim is to have multiple packages which can be put together to create something bigger by defining only the structure.

Micropackages are maintained by [BracketSpace](https://bracketspace.com).

## 📖 Changelog

[See the changelog file](./CHANGELOG.md).

## 📃 License

This software is released under MIT license. See the [LICENSE](./LICENSE) file for more information.
