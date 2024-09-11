# Image uploads

## Set the disk

By default, Canvas will attempt to use the disk defined in `nova.storage-disk` config.

You can override this using the `->disk(...)` method:

```PHP
Canvas::make('Content')
    ->disk('public')
```

You can also pass a path as the optional second parameter:

```PHP
Canvas::make('Content')
    ->disk('public', 'images')
```

## Optimisation

Canvas uses [Spatie image optimizer](https://github.com/spatie/laravel-image-optimizer) to automatically optimise 
uploaded images, which is essential for performance on your applications front-end.

<procedure title="Configure image optimisation">
<step>
Publish the config file:
<code-block lang="bash">
php artisan vendor:publish --provider="Spatie\LaravelImageOptimizer\ImageOptimizerServiceProvider"
</code-block>
</step>
<step>
Update <code>config/image-optimizer.php</code>
</step>
</procedure>

<warning>
Image optimisation might not work out the box, <a href="https://github.com/spatie/image-optimizer?tab=readme-ov-file#optimization-tools">read the Spatie docs</a> to set up the optimisation tools on your system.
</warning>

## Using your own endpoint

The build-in endpoint should work fine for most use-cases, but its completely replaceable if you want to add
additional functionality.

You can simply change the endpoint path in the `nova-canvas.images.endpoint` config.

Your endpoint should accept a POST request with the following:

- $FILE (`image`) - The image to upload.
- $POST (`disk`) - The disk to upload images to.
- $POST (`path`) - The path to upload images to.

If the upload is successful it should respond with `200 OK` and a public path to the uploaded image as JSON: 
```json
{ "path": "images/my-image.jpg" }
```

If something goes wrong it should respond with `422 Unprocessable Content` or `500 Internal Server Error`, you can also provide an error message as JSON:
```json 
{ "error": "Image must be smaller than 10MB" }
```

<warning>
Using your own endpoint will bypass some features like optimisation, you will need to re-implement these yourself.
</warning>