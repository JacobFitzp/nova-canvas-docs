# Configuration

## Basic

### Full-width / stacked

If things start to feel squished, you might want to make use of the full-width / stacked layouts to give it more space.

```PHP
Canvas::make('Content')
    ->stacked()
    ->fullWidth(),
```

<tabs>
    <tab title="Default">
        <img src="Screenshot_2024-07-16_at_20.56.39.png" />
    </tab>
    <tab title="Stacked">
        <img src="Screenshot_2024-07-16_at_20.58.05.png" />
    </tab>
    <tab title="Full-width">
        <img src="Screenshot_2024-07-16_at_20.59.06.png" />
    </tab>
    <tab title="Both">
        <img src="Screenshot_2024-07-16_at_20.59.53.png" />
    </tab>
</tabs>

### Read-only

If you want to disable editing you can simply use `->readonly()`

```PHP
Canvas::make('Content')
    ->readonly(),
```

## Advanced

- [Toolbar](Toolbar.md)
- [Character count](Character-count.md)
- [Image uploads](Image-uploads.md)
- [Styling](Styling.md)
- [Output](Output.md)