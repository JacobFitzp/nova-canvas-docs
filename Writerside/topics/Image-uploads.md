# Image uploads

By default, Canvas will attempt to use the disk defined in `nova.storage-disk` config.

## Set the disk

## Optimisation



## Using your own endpoint

The build-in endpoint should work fine for most use-cases, but its completely replaceable if you want to add
additional functionality.

You can simply change the endpoint path in the `nova-canvas.images.endpoint` config.

Your endpoint should accept a POST request with the following:

- $FILE (`image`) - The image to upload.
- $POST (`disk`) - The disk to upload the image to, passed along when you do `->disk(...)`

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