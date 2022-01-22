# Quick Start

Creating a Famenun app is damn easy. Just follow the guide and your app will be ready in not more than 5 minutes.

## Famenun CLI

First of all we ll install [@famenun/cli](https://www.npmjs.com/package/@famenun/cli) using NPM. It will help us in setting up the project for us.

`npm i @famenun/sdk`

## Create Project

Once the [@famenun/cli](https://www.npmjs.com/package/@famenun/cli) is installed we ll create a new project using [@famenun/cli](https://www.npmjs.com/package/@famenun/cli).
``` sh
mkdir awesome-app
cd awesome-app
famenun create awesome-app -y
```

If you open the `awesome-app` folder you will see the following directory structure

```
...
+-- awesome-app
|   +-- f.app.json
|   +-- sdk.js
|   +-- index.html
|   +-- ...
...

```

You will learn about these files in details in the following docs pages.

## Build

Now we ll build the app using [@famenun/cli](https://www.npmjs.com/package/@famenun/cli) with the following command

`famenun build .`

And you will see a new file in the directory called `awesome-app.fap`. You will learn more about `.fap` file in the upcoming docs pages.

## Test

Just copy this file to your android device and head over to Famenun app and go to `Settings>Installed App` and then click on `Add` button. Select the `awesome-app.fap` file and you have your first Famenun up and running.

Congratulations on building your first Famenun app 🎉