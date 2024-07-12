# Toolbar

Configure the toolbar using the `->toolbar(...)` method, passing an array or comma-separated list of tools.

```PHP
Canvas::make('Content')
    ->toolbar('format,|,bold,italic'),
```

Use `|` or `separator` to add a visual divider between tools.

[Read more about the available tools here.](Tools.md)