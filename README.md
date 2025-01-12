# google_maps_flutter_example

A new Flutter application to demonstrate how to implement flutter google maps in a flutter application and perfoem advanced tasks on it.

## Adding Map To the App

1. Get an API key at https://cloud.google.com/maps-platform/.

2. Enable Google Map SDK for each platform.
   - Go to [Google Developers Console.](https://console.cloud.google.com/)
   - Choose the project that you want to enable Google Maps on.
   - Select the navigation menu and then select "Google Maps".
   - Select "APIs" under the Google Maps menu.
   - To enable Google Maps for Android, select "Maps SDK for Android" in the "Additional APIs" section, then select "ENABLE".
   - To enable Google Maps for iOS, select "Maps SDK for iOS" in the "Additional APIs" section, then select "ENABLE".
   - Make sure the APIs you enabled are under the "Enabled APIs" section.

3. In `android/app/src/main/AndroidManifest.xml` inside `Application tag` add your key
```xml
<manifest ...
  <application ...
    <meta-data android:name="com.google.android.geo.API_KEY"
               android:value="YOUR KEY HERE"/>
```

4. In `ios/Runner/AppDelegate.swift` addthe following lines 
```swift
import UIKit
import Flutter
import GoogleMaps

@UIApplicationMain
@objc class AppDelegate: FlutterAppDelegate {
  override func application(
    _ application: UIApplication,
    didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?
  ) -> Bool {
    GMSServices.provideAPIKey("YOUR KEY HERE")
    GeneratedPluginRegistrant.register(with: self)
    return super.application(application, didFinishLaunchingWithOptions: launchOptions)
  }
}
```
5. Use the `GoogleMapsWidget.dart` inside the `lib/widget` folder as normal widget and use it where you want.
