# APIs

Here are the awesome APIs which can be accessed through [@famenun/sdk](https://www.npmjs.com/package/@famenun/sdk)

## ToastHandler

It can be used to show a simple message to the user. It has been developed just to tested whether the SDK is initalised properly.

``` js
  // pseudo class
  class ToastHandler {
    // pseudo function
    showToast(message: string): Promise<void> { // argument message is the string to be shown as toast
      ...
    }
  }

  // example usuage
  api.toastHandler.showMessage("this is a test message")
  .then(() => {
    console.log("toast message shown successfully :)");
  });
```

## PublishHandler
It can be used to show user a prompt to broadcast something in their profile

``` js
  // pseudo class
  class PublishHandler {
    // pseudo function
    publish(files: Array<string>): Promise<void> { // argument files is an array of file urls [can be blob-urls or remote-urls]
      ...
    }
  }

  // example usuage
  api.publishHandler.publish(["https://mydomain.com/files/myphoto.png"])
  .then(() => {
    console.log("publish prompt made successfully :)");
  });
```

## ProfileHandler

It can be used get currently logged in user profile info and manage current user profile shortcut/extensions

``` js
// pseudo class
  class ProfileHandler {
    // pseudo function
    getProfile(): Promise<any> { 
      ...
    }
    // pseudo function
    createShortcut(profileShortcut: ProfileShortcut): Promise<void> { // argument profileShortcut contains info about the profile extension
      ...
    }
  }

  // example usuage
  api.profileHandler.getProfile()
  .then((profile: any) => {
    // here you get the profile info of the currently logged in user
  });

  api.profileHandler.createShortcut({
    "dp": "https:// || blob://" // dp url of the profile extension
    "na": "My Store", // name of the extension
    "pa": "./index.html?profile={uid}" // relative path of the page to be opend, {uid} is an available wildcard which ll be replaced with the currently logged in user's uid
  })
  .then(() => {
    console.log("added profile extension successfully :)");
  });
```

## PaymentHandler

It can be used to prompt user to pay for some service.

``` js
  // pseudo class
  class PaymentHandler {
    // pseudo function
    makePayment(payable: Payable): Promise<void> { // argument payable contains info about the transaction
      ...
    }
  }

  // example usuage
  api.paymentHandler.makePayment({
    "id": "transaction_ref_id", // this is the most important thing as this ll let the develoer know whether the transaction done or failed.
    "cu": "INR", // currency of the transaction
    "am": 501, // amount in number
    "re": "receiver_uid", // platform uid of the person to whom the money ll be sent
    "su": "buying platform cash" // reason of transaction
  })
  .then(() => {
    console.log("payment prompt made successfully :)");
  });
```

## NotificationHandler
It can be used to notify a user about anything important or re-engage them in your app

``` js
  // pseudo class
  class NotificationHandler {
    // pseudo function
    notify(notifiable: Notifiable): Promise<void> { // argument notifiable contains info about the notification
      ...
    }
  }

  // example usuage
  api.notificationHandler.notify({
    "title": "New Friend request", // notification title
    "body": "you have received a new friend request", // details of the notification
    "image": "https://...", //image attachment url
    "path": "./notifications.html" //path to be opened on click
  })
  .then(() => {
    console.log("user notified successfully :)");
  });
```

## LinkHandler

It can be used to open a link in browser and generate deep links for the app

``` js
  class LinkHandler {
    // pseudo function
    openLink(link: string): Promise<void> { // argument link is the url to be opened in browser
      ...
    }
  }

  // example usuage
  api.linkHandler.openLink("https://famenun.com")
  .then(() => {
    console.log("link opened successfully :)");
  });
```

## DatabaseHandler

it can be used to save and retrive key/value pairs

``` js
  // pseudo class
  class DatabaseHandler {
    // pseudo function
    insertData(insertable: Insertable): Promise<void> { // argument insertable is the object containing info about the data to be saved
      ...
    }
    // pseudo function
    getData(key: string): Promise<string> { // argument key is the string of which the value has to be retrived
      ...
    }
  }

  // example usuage
  api.databaseHandler.insertData({
    "key": "__user_id__", // key whose value has to be saved
    "value": "drona2938" // the value to be saved
  })
  .then(() => {
    console.log("data saved successfully :)");
  });
  api.databaseHandler.getData("__user_id__")
  .then((value) => {
    // here you get the value of the key
  });
```

## CircleHandler

it can be used to get users friend's uid list

``` js
  // pseudo class
  class CircleHandler {
    // pseudo function
    getCircle(): Promise<string[]> {
      ...
    }
  }

  // example usuage
  api.circleHandler.getCircle()
  .then((circle: string[]) => {
    // here you receive user's circle [uids of their friends]
  });
```

## ChatroomHandler

it can be used to open chat with other users

``` js
  // pseudo class
  class ChatroomHandler {
    // pseudo function
    openChat(...users: Array<string>): Promise<void> {
      ...
    }
  }

  // example usuage
  api.chatroomHandler.openChat("user_uid_01", "user_uid_02")
  .then(() => {
    console.log("chat opened successfully :)");
  });
```

## AppGalaxyHandler

it can be used to get installed apps of the user, open an app and app's galaxy profile

``` js
  // pseudo class
  class AppGalaxyHandler {
    // pseudo function
    getInstalledApps(): Promise<Array<any>> { // it prompts user to allow app to access the installed apps
      ...
    }
    // pseudo function
    openApp(app: string): Promise<void> { // argument app is the id of the app to be opened
      ...
    }
    // pseudo function
    openAppProfile(app: string): Promise<void> { // argumet app is the id of the app profile to be opened
      ...
    }
  }

  // example usuage
  api.appGalaxyHandler.getInstalledApps()
  .then((apps: any[]) => {
    // here you get the list of installed apps of the user
  });
  api.appGalaxyHandler.openApp("com.example.myapp")
  .then(() => {
    console.log("app started successfully :)");
  });
  api.appGalaxyHandler.openAppProfile("com.example.myapp")
  .then(() => {
    console.log("app profile opened successfully :)");
  });
```