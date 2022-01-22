# SDK

[@famenun/sdk](https://www.npmjs.com/package/@famenun/sdk) is the bridge between your app and the Famenun vOS. It provides awesome abilities to apps to interact with Famenun vOS

## Installation

One can install [@famenun/sdk](https://www.npmjs.com/package/@famenun/sdk) from NPM 

`npm i @famenun/cli`

or can download the [sdk.js](https://static.famenun.com/sdk.js) file and include it direcly in the app

## Usage

While using through NPM

``` js
import * as SDK from "famenun/sdk"
const api = SDK.init("your app id", true); // pass false in disable debug mode

// call the function on a button click
api.toastHandler.showToast("This is a test message")
    .then(() => {
        // toast has been shown to the user
    })
```

While using though js file


``` html
<script src="./famenun_sdk.js"></script>
<script>
        const api = __famenun__.init("your app id");
        // call the function on a button click
        api.toastHandler.showToast("This is a test message")
            .then(() => {
                // toast has been shown to the user
            })
</script>
```