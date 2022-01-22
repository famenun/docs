# Hooks

Developers can insert data into the user flow like feeds, profile or search pages. Here is a snippet of how hooks work.

``` js
  // feeds.js
  __famenun__.emit({
    error: false,
    message: "data coming from feeds hook",
    type: "HOOK_EMISSION",
    data: {
        "id": "first",
        "layout": {
          "content": "this is a test title"
        }
    }
  });
```