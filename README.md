# Arabic Reading Coach — Android App (Work In Progress)

Android application for the Arabic Reading Coach web platform.

The app provides a native Android wrapper around:

https://arabic-reading.nafishaider.com/

It is designed to give users a simple installable Android application while keeping the main Arabic Reading Coach application hosted and updated through the web platform.

---


## Overview

Arabic Reading Coach is a mobile-friendly Arabic reading application designed to help learners practise Arabic pronunciation and reading.

The Android app loads the live Arabic Reading Coach platform inside a secure Android WebView.

This means improvements made to the web application are automatically available to Android users without requiring a new APK release for normal website updates.

<img width="1691" height="1078" alt="image" src="https://github.com/user-attachments/assets/6c6b544b-0c78-41c1-a01c-14c2a67107ea" />


---

## What this app does

- Opens Arabic Reading Coach in a full-screen Android app
- Supports microphone access
- Supports Arabic reading and pronunciation features
- Supports audio playback
- Works on Android phones and tablets
- Opens external links in the normal browser
- Shows an offline message if there is no internet connection

## How it works

```text
Android App
    ↓
WebView
    ↓
https://arabic-reading.nafishaider.com/
```

The main app is hosted online.

This means website updates can appear in the Android app without rebuilding the APK.

## Install the app

Download the APK:

```text
ArabicReading.apk
```

Copy it to your Android phone and open it.

Android may ask you to allow installation from unknown sources.

Once installed, open:

**Arabic Reading Coach**

## Microphone Permission

The first time you use a reading feature, Android may ask:

```text
Allow Arabic Reading Coach to record audio?
```

Tap:

```text
Allow
```

Microphone access is required for reading and pronunciation features.


## Apple Device & Install
XCode is given - You can install but bit of a mission

How to install it on an iPhone
Unlike Android APKs, Apple requires the app to be signed.
On a Mac:
1. Extract the ZIP.
2. Open:
   ArabicReadingCoach.xcodeproj
3. In Xcode select ArabicReadingCoach → Signing & Capabilities.
4. Select your Apple Developer Team.
5. Connect your iPhone.
6. Select your iPhone at the top of Xcode.
7. Press ▶ Run.

   
## Main Website

https://arabic-reading.nafishaider.com/


## License

MIT License

Copyright © 2026 Nafis Haider
