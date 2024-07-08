# Mirrorfly Sample App

## Overview
Our sample app provides basic UI integrated with latest Mirrorfly SDK where you can customize and build your own app easily.

## Before getting started

This section shows you the prerequisites you need for testing **Mirrorfly Sample App**.

### Requirements
The minimum requirements to run the Sample App:

```groovy
- Xcode 14.1 or later
- iOS 12.1 or later
- Swift 5.0 or later
```
> **Note :** Before proceeding with CONTUS MirrorFly Chat SDK integration, there must be an SDK license key that needs to be obtained for your MirrorFly application.

## Getting started
This section explains the steps you need to take before testing the sample app.

**Step 1:** Create a new project
To get started, open Xcode, create a new Swift Project


**Step 2:** If you have not initiated any pods project before, then initiate the one. Now, add the required pods that are necessary for the SDK to execute the process perfectly.

```gradle
pod 'MirrorflyUIKit', '3.2.0'
   ```

Add the below given pod hook code block at the end of the pod file and thus, finally install the pods.

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
