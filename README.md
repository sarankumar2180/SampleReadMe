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
dependencyResolutionManagement {
        repositories {
            mavenCentral()
               maven {
                 url "https://repo.mirrorfly.com/release"
                 }
       }
}
   ```

**Step 3:** Add the following dependencies in the app/build.gradle file.
   ```gradle
 apply plugin: 'com.android.application'

android {
    buildFeatures {
        viewBinding true
    }

    compileOptions {
        sourceCompatibility JavaVersion.VERSION_1_8
        targetCompatibility JavaVersion.VERSION_1_8
    }
}

dependencies {
      implementation 'com.mirrorfly.sdk:MirrorFlySDK:7.13.0'
}
   ```

**Step 4:** Add the below line in the gradle.properties file, to avoid imported library conflicts.
   ```gradle
   android.enableJetifier=true
   ```

**Step 5:** Open the AndroidManifest.xml and add below permissions.
   ```xml
   <uses-permission android:name="android.permission.INTERNET" />
   ```
**Step 6:** To log in and run the app, you need to add the **LICENCSE** key in the app/build.gradle file. To generate the license key, you need to sign up in the <a href="https://console.mirrorfly.com/" target="_self">MirrorFly console</a>, and you can get it from there.
   ```gradle
        debug {
            buildConfigField 'Boolean', 'IS_QA_BUILD', 'true'
            buildConfigField 'String', 'LICENSE', '"Please enter your License key"' // add your license key
            buildConfigField 'String', 'WEB_CHAT_LOGIN', '"https://webchat-preprod-sandbox.mirrorfly.com/"'
            buildConfigField "String", "SUPPORT_MAIL", '"contussupport@gmail.com"'
            resValue("string", "app_name", "UI Kit")
            shrinkResources false
            debuggable true
            minifyEnabled false
            signingConfig signingConfigs.config
            proguardFiles getDefaultProguardFile('proguard-android.txt'), 'proguard-rules.pro'
        }
```
After saving your build.gradle file, click the Sync button to apply all the changes.
