# Basic usage

You can start using Canvas immediately within your Nova resource, it comes pre-configured out of the box to suit most use-cases.

```php
use Jacobfitzp\NovaCanvas\Canvas;

// ...

public function fields(NovaRequest $request): array
{
    return [
        Canvas::make('Content'),
    ];
}
```

Content will be stored as raw HTML, or JSON, it's recommended to use a `TEXT` column  (or equivalent) in your database.