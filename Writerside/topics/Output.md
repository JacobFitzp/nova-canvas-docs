# Output

By default, the Canvas field outputs a string of HTML. This is great for most use-cases, since you can easily render it on your applications front-end.

However, Canvas also supports JSON output, using the `->asJson()` method.

```PHP
Canvas::make('Content')
    ->asJson()
```

You will also need to add a `json` cast for this to work properly.

[Read more about outputting JSON vs HTML.](https://tiptap.dev/docs/guides/output-json-html#option-1-json)