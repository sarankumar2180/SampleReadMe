# Mirrorfly Sample App

## Overview
Our sample app provides basic UI integrated with latest Mirrorfly SDK where you can customize and build your own app easily.

## Before getting started

This section shows you the prerequisites you need for testing **Mirrorfly Sample App**.

### Requirements
The minimum requirements to run the Sample App:

```groovy
- Xcode 15 or later
- iOS 13.0 or later
- Swift 5.0 or later
```

## Getting started

This section gives you information you need to get started with MirrorFly UIKit for iOS.

**Try the sample app**

Our sample app has all the core features of MirrorFly UIKit for iOS. Download the app from our GitHub repository to get an idea of what you can build with the actual UIKit before building your own project.

**Step 1:** Install UIKit for iOS

UIKit for iOS can be installed through <a href="https://cocoapods.org/" target="_self">CocoaPods</a>

**- CocoaPods**

1. Add `MirrorflyUIKit` into your `Podfile` in Xcode as below:

```gradle
platform :ios, '13.0'
use_frameworks!

target YOUR_PROJECT_TARGET do
    pod 'MirrorflyUIKit'
end
   ```
2. Install the `MirrorflyUIKit` framework through CocoaPods.
```gradle
$ pod install
```

3. Add the below given pod hook code block at the end of the pod file and thus, finally install the pods.

```gradle
post_install do |installer|
  installer.pods_project.targets.each do |target|
    target.build_configurations.each do |config|
      config.build_settings['IPHONEOS_DEPLOYMENT_TARGET'] = '12.1'
      config.build_settings['ENABLE_BITCODE'] = 'NO'
      config.build_settings['APPLICATION_EXTENSION_API_ONLY'] = 'No'
      config.build_settings['BUILD_LIBRARY_FOR_DISTRIBUTION'] = 'YES'
    end
  end
end

```

**Step 3:** Adding **Photo library usage description** to your info.plist
   ```gradle
Privacy - Photo Library Usage description 
   ```

**Step 4:** Initialize with License Key.

You can copy the license key from the **'Overview’** section in the Console dashboard.
   ```gradle
let LICENSE_KEY = "xxxxxxxxxxxxxxxxxxxxxx" //"YOUR_LICENSE_KEY"
let USER_ID = "xxxxxxxxxxxxxxxxxxxxxx"
   ```
To integrate and run Mirrorfly UIKit in your app, you need to initialize it first. Initialize the MirrorFlyUI instance through your view controller
