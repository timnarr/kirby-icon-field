![Kirby Icon Field Banner](/.github/banner.png)

# Kirby Icon Field

A simple Icon field for Kirby - throw your Icon pack in a folder, add the field to your blueprints and you're good to go.

> 🚨 This plugin is untested on Kirby < v4-alpha.2 so far and might not work as expected. I don't plan on adding support for Kirby 3 versions (except if provided with a PR).

## Installation

#### Recommended: Composer

```
composer require tobimori/kirby-icon-field
```

#### Manual installation

Download and copy this repository to `/site/plugins/kirby-icon-field`, or apply this repository as Git submodule.

## Usage

This plugin relies on having your SVG icons as separate files in a folder for display in the panel - of course you're free to do whatever you want with the field's value in your templates.

Your icons should use `currentcolor` for defining the color of a fill/stroke so they can inherit the correct color from the panel.

#### Add the field to your blueprint:

```yaml
fields:
  icon:
    label: Icon
    type: icon
    folder: assets/icons # path to your icon folder, relative to the `index` kirby root
    max: 1 # max number of icons to select - 1 will look like a 'select field', none or more like a 'multiselect' field
    # [more settings...] - same as multi-select field, e.g. disabling search, limiting icons, etc.
```

#### Use the field value in your panel

```php
<?= svg('/assets/icons/' . $page->icon()) ?>
```

## Options

| Option   | Default       | Description                                           |
| -------- | ------------- | ----------------------------------------------------- |
| `cache`  | `true`        | Enable cache for reading from icons directory         |
| `folder` | `assets/icon` | Default folder for icon field, can also be a function |

Options allow you to fine tune the behaviour of the plugin. You can set them in your `config.php` file:

```php
return [
    'tobimori.icon-field' => [
        'cache' => true,
        'folder' => 'assets/icon'
    ],
];
```

## Support

> This plugin is provided free of charge & published under the permissive MIT License. If you use it in a commercial project, please consider to [sponsor me on GitHub](https://github.com/sponsors/tobimori) to support further development and continued maintenance of my plugins.

## License

[MIT License](./LICENSE)
Copyright © 2023 Tobias Möritz

The icons in the preview image are part of [Chunk Icons](https://www.figma.com/community/file/889863427421594653/Chunk-Icons) by [Noah Jacobus](https://twitter.com/Jabronus). <3
