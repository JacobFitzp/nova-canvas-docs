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

Content will be stored as raw HTML, it's recommended to use a `TEXT` column  (or equivalent) in your database.

## Note on image uploads

By default, it will attempt use the storage disk configured in your existing nova config `nova.storage_disk`. Assuming 
this disk is configured correctly image uploads will work out of the box.

[Read more about configuring image uploads here.](Image-uploads.md)