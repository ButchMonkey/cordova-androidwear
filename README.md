
# Cordova Android Wear Plugin

The plugin has functions that allows your app to have bidirectional communication with Android Wear Smartwatch applications and Cordova applications.

## Now works with Google Play Services v11.8.0
Updated on Jan 04 2018 for use with the latest version of Google Play Services (v11.8.0).
Unfortunately NodeApi has been deprecated (MessageApi as well, but it only gives a warning), so I had to change the code myself. Later I might modify the code again when a newer version of Google Play Services is released.

## Installation
With Cordova CLI:
```
cordova plugin add https://github.com/ragcsalo/cordova-androidwear
```

## Usage

1. Add the plugin to your cordova project.

2. Bundle your watch apk in your project by following the instructions in the [documentation](https://developer.android.com/training/wearables/apps/packaging.html).

## Example
  ```javascript
  AndroidWear.onConnect(function(e) {
      alert("Connection Successfully Established - handle: " + e.handle);

      AndroidWear.onDataReceived(e.handle, function(e) {
          alert("Data received - handle: " + e.handle + " data: "+ e.data);
      });

      AndroidWear.sendData(e.handle, "Hello From Cordova!");
  });
  ```
