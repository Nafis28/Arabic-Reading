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

## Build the app

You can build the Android app using:

- Google Colab
- Android Studio

The project uses:

```text
Java 17
Android SDK 36
Minimum Android SDK 24
```

Package name:

```text
com.nafishaider.arabicreading
```

## Main Website

https://arabic-reading.nafishaider.com/

## Updating the app

Most website changes do not require a new APK.

Simply update the live website:

```text
arabic-reading.nafishaider.com
```

The Android app will load the latest version.

You only need to rebuild the Android app when changing things such as:

- App name
- App icon
- Android permissions
- Native Android features
- Package name
- Android SDK version

## Open Source

This project is open source under the **MIT License**.

You are free to:

- Use it
- Modify it
- Fork it
- Share it
- Use it in your own projects

See the `LICENSE` file for full details.

## License

MIT License

Copyright © 2026 Nafis Haider

This version is much better for a public GitHub repo because someone can understand what the project does within a few seconds.
