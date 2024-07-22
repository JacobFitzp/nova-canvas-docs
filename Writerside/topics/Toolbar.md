# Toolbar

Configure the toolbar using the `->toolbar(...)` method, passing an array or comma-separated list of tools.

```PHP
Canvas::make('Content')
    ->toolbar('format,|,bold,italic'),
    // Or ...
    ->toolbar(['format', '|', 'bold', 'italic']),
```

Use `|` or `separator` to add a visual divider between tools.

[Read more about the available tools here.](Tools.md)

## Using presets

In-addition to manually passing a list of options you can also define a reusable preset.
This can be done by updating `config/nova-canvas.php` and adding a new option under toolbars:

```php
// In config/nova-canvas.php
return [
    'toolbars' => [
        'default' => [ /* ... */ ],
        'my-preset' => ['format', 'image'],
    ],
];

// In your Nova resource fields
Canvas::make('Content')
    ->toolbar('my-preset'),
```

Note that the `default` preset must always be defined, this is used as the default when no override is specified.