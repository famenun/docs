# Manifest

The file `f.app.json` is the manifest file of the app. it tells the Famenun vOS about the basic information about the app.

Here is an example of `f.app.json`

``` json
  {
    // NOTE: ALL THE PATHS SHOULD BE RELATIVE TO THE f.app.json FILE
    /*version of the app release*/
    "version": "1.0.0",
    /*id of the app*/
    "id": "com.example.app",
    /*name of the app*/
    "name": "Test App",
    /*path of the app*/
    "icon": "./icon.png",
    /*path of the entry file*/
    "entry": "./index.html",
    /*theme color of the app shold have all the six color digits*/
    "color": "#ff659a", // this color code must have all the 7 chars starting from # for ex #fff is invalid and #ffffff is valid
    /*for hooking data in the famenun system like data in the feeds*/
    "hooks": {
        "feeds": "./hooks/feeds.js"
      }
  }
```