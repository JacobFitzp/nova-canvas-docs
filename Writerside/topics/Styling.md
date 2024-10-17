# Styling

The styling of Canvas is intended to be consistent with the rest of Nova, so it looks and feels first-party.

## Scrollable

By default, the editor grows to accommodate the content. 
However, you can opt to restrict it to a fixed height and use a scrollbar instead:

```php
Canvas::make('Content')
    ->scrollable()
```

This will fix the editor at 400px, but you can pass in any height you like as an optional parameter.

## Content

The content is styled using [Tailwind's typography extension](https://v1.tailwindcss.com/docs/typography-plugin).

If you want to apply custom styling you can [register your own assets](https://nova.laravel.com/docs/customization/assets.html), everything is nested under the `.nova-canvas-content` class.
