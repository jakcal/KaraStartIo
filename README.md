# Flutter - StartIo SDK Plugin

Flutter plugin for StartIo SDK.

Currently, this plugin only support Android platform. 
## How to use the plugin 
* Installing the plugin: 



Just un-zip the file and add it to the root folder of the app


```yaml
  kara_start_io_plugin:
    path: ./kara_start_io_plugin
    
```



* Updating AndroidManifest.xml file

_Base on [StartIo SDK document](https://support.startapp.com/hc/en-us/articles/360002411114-Android-Standard-#Step1,AddingandInitializingtheSDKtoYourProject)_

Add following meta-data tag with your StartIo App Id under the <application> section in your manifest file:
```xml
<meta-data android:name="com.startapp.sdk.APPLICATION_ID" android:value="startapp_app_id" />
```

If you want to disable return ads (they are enabled by default) please add following meta-data tag:
```xml
<meta-data android:name="com.startapp.sdk.RETURN_ADS_ENABLED" android:value="false" />
```

If you want to disable splash ads (they are enabled by default) please add following meta-data tag:
```xml
<meta-data android:name="com.jakcal.karastartio.SPLASH_AD_ENABLED" android:value="false" />
```

* Banner as widget
```dart
import 'package:kara_start_io_plugin/kara_start_io_plugin.dart';
...

// StartIo AdBanner as widget
AdBanner(),
```

* Load interstitial ad
```dart
import 'package:kara_start_io_plugin/kara_start_io_plugin.dart';
...
await StartApp.showInterstitialAd();
```

* Load rewarded video ad
```dart
import 'package:kara_start_io_plugin/kara_start_io_plugin.dart';
...
await StartApp.showRewardedAd(onVideoCompleted: () {
    // video completed callback
}, onReceiveAd: () {
    // ad received callback
}, onFailedToReceiveAd: (String error) {
    // failed to received ad callback
});
```
