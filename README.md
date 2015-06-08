# NativeScript Social Share

A NativeScript module to use the native social sharing widget on Android and iOS. Currently this module supports image and text sharing.

## Installation

Run `npm install nativescript-social-share --save` from your project's inner `app` directory:

```
.
├── app  <----------------run npm install from here
│   ├── App_Resources
│   │   ├── android
│   │   └── ios
│   ├── app.css
│   ├── app.js
│   ├── main-page.js
│   ├── main-page.xml
│   ├── node_modules
│   │   └── nativescript-social-share <-- The install will place the module's code here
│   │       └── ...
│   ├── package.json <-- The install will register “nativescript-social-share” as a dependency here
│   └── tns_modules
│       └── ...
└── platforms
    ├── android
    └── ios
```

As is, using npm within NativeScript is still experimental, so it's possible that you'll run into some issues. A more complete solution is in the works, and you can check out [this issue](https://github.com/NativeScript/nativescript-cli/issues/362) for an update on its progress and to offer feedback.

If npm doesn't end up working for you, you can just copy and paste this repo's social-share.android.js and social-share.ios.js files into your app and reference them directly.

## Usage

To use the social share module you must first `require()` it. After you `require()` the module you have access to its APIs.

``` js
var socialShare = require("./node_modules/nativescript-social-share/social-share");
```

## API

### shareImage(ImageSource image, [optional] String subject)

The `shareImage()` method expects an [`ImageSource`](http://docs.nativescript.org/ApiReference/image-source/ImageSource.html) object. The code below loads an image from the app and invokes the share widget with it:

``` js
var socialShare = require("./node_modules/nativescript-social-share/social-share");
var imageSource = require("image-source");

var image = imageSource.fromFile("~/path/to/myImage.jpg");
socialShare.shareImage(image);
```

You can optionally provide a second argument to configure the subject on Android:

``` js
socialShare.shareImage(image, "How would you like to share this image?");
```

### shareText(String text, [optional] String subject)

The `shareText()` method expects a simple string:

``` js
var socialShare = require("./node_modules/nativescript-social-share/social-share");
socialShare.shareText("I love NativeScript!");
```

Like `shareImage()`, you can optionally pass `shareText()` a second argument to configure the subject on Android:

``` js
socialShare.shareText(image, "How would you like to share this text?");
```

## Screenshots

<div>
	<img alt="" src="screenshots/ios.png" style="max-width: 50%; height: 500px; float: left;">
	<img alt="" src="screenshots/android.png" style="max-width: 50%; height: 500px; float: left;">
</div>