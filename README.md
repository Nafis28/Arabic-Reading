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

## App Architecture

```text
Android App
    |
    v
Native Android WebView
    |
    v
https://arabic-reading.nafishaider.com/
    |
    v
Arabic Reading Coach Web Application
    |
    +-- Arabic lessons
    +-- Reading exercises
    +-- Audio playback
    +-- Microphone input
    +-- Pronunciation / reading analysis
```

---

## Features

- Native Android application
- Full-screen WebView
- JavaScript support
- DOM storage support
- Cookie and session support
- Microphone permission support
- WebRTC audio capture support
- Optional camera support
- File upload support
- Android back-button navigation
- Loading progress indicator
- Offline error screen
- External links open in the user's browser
- HTTPS-only application traffic
- Hardware-accelerated WebView
- Responsive mobile and tablet support

---

## Live Application

The Android app opens:

```text
https://arabic-reading.nafishaider.com/
```

The website remains the primary application.

The Android application acts as the mobile application shell around the hosted platform.

---

## Microphone Support

Microphone access is required for reading and pronunciation features.

When the web application requests microphone access:

```text
User selects Start Reading
        |
        v
Website requests microphone
        |
        v
Android permission prompt
        |
        v
User selects Allow
        |
        v
Android WebView grants microphone access
        |
        v
Arabic Reading Coach receives audio
```

Microphone WebView permission is restricted to:

```text
https://arabic-reading.nafishaider.com/
```

External websites are not automatically given microphone access.

---

## Android Permissions

The application may request the following permissions:

### Internet

```xml
android.permission.INTERNET
```

Required to access the hosted Arabic Reading Coach application.

### Network State

```xml
android.permission.ACCESS_NETWORK_STATE
```

Used to assist with detecting network availability.

### Microphone

```xml
android.permission.RECORD_AUDIO
```

Required for Arabic reading and pronunciation functionality.

### Audio Settings

```xml
android.permission.MODIFY_AUDIO_SETTINGS
```

Used for WebRTC and microphone-based audio functionality.

### Camera

```xml
android.permission.CAMERA
```

Included for optional/future web application functionality.

The camera is not automatically activated.

---

## Android Configuration

Current project configuration:

```text
Application Name:
Arabic Reading Coach

Package Name:
com.nafishaider.arabicreading

Minimum Android SDK:
API 24

Target Android SDK:
API 36

Compile Android SDK:
API 36

Java:
Java 17
```

---

## Project Structure

Typical project structure:

```text
ArabicReadingAndroid/
|
+-- app/
|   |
|   +-- src/
|   |   |
|   |   +-- main/
|   |       |
|   |       +-- java/
|   |       |   |
|   |       |   +-- com/
|   |       |       +-- nafishaider/
|   |       |           +-- arabicreading/
|   |       |               +-- MainActivity.java
|   |       |
|   |       +-- res/
|   |       |   |
|   |       |   +-- drawable/
|   |       |   +-- layout/
|   |       |   +-- values/
|   |       |
|   |       +-- AndroidManifest.xml
|   |
|   +-- build.gradle
|
+-- build.gradle
+-- settings.gradle
+-- gradle.properties
+-- README.md
```

---

## MainActivity

`MainActivity.java` manages the Android WebView.

Responsibilities include:

- Loading the Arabic Reading Coach website
- Enabling JavaScript
- Enabling DOM storage
- Managing cookies
- Handling WebRTC microphone access
- Requesting native Android permissions
- Handling file uploads
- Opening external links
- Managing page loading
- Displaying offline/error pages
- Handling Android back navigation
- Saving WebView state

---

## Building the App

The project can be built using Android Studio or Google Colab.

---

# Build with Android Studio

## Requirements

Install:

- Android Studio
- Android SDK 36
- Java 17
- Android Build Tools

Clone the repository:

```bash
git clone YOUR_REPOSITORY_URL
```

Open the project in Android Studio.

Allow Gradle to sync.

Then select:

```text
Build
>
Build Bundle(s) / APK(s)
>
Build APK(s)
```

The APK will normally be generated under:

```text
app/build/outputs/apk/debug/
```

---

# Build with Google Colab

A Google Colab build script can also be used to automatically:

1. Install Java
2. Install the Android SDK
3. Install Gradle
4. Generate the Android project
5. Compile the application
6. Produce an installable APK

Example output:

```text
ArabicReading.apk
```

---

## Installing the Test APK

Copy the APK to an Android device.

Open:

```text
ArabicReading.apk
```

Android may display:

```text
Allow installation from this source
```

Enable the permission for the application being used to install the APK.

Then install Arabic Reading Coach.

---

## First Launch

When launched, the app opens:

```text
https://arabic-reading.nafishaider.com/
```

No additional configuration should normally be required.

When a reading feature requests microphone access, Android will display a permission prompt.

Select:

```text
Allow
```

to enable reading recognition.

---

## Updating the Web Application

One of the main advantages of this architecture is that frontend application changes generally do not require rebuilding the Android app.

For example:

```text
Developer updates Arabic Reading Coach
        |
        v
Deploy to Cloudflare
        |
        v
arabic-reading.nafishaider.com updated
        |
        v
Android users automatically receive latest version
```

A new Android APK is generally only required when changing native functionality such as:

- Android permissions
- Package name
- App icon
- Splash screen
- Native notifications
- Android integrations
- WebView configuration
- App signing
- Android SDK target
- Google Play configuration

---

## Security

The application is designed to load the primary platform over HTTPS.

Primary trusted origin:

```text
https://arabic-reading.nafishaider.com
```

Security controls include:

- HTTPS traffic
- HTTP mixed content blocked
- Android Safe Browsing
- Restricted microphone WebView permissions
- File-system access disabled
- External websites opened outside the app
- Web permissions restricted to trusted application origin

---

## WebView Updates

Android WebView is provided by Android System WebView or Google Chrome on most Android devices.

Users should keep the following updated:

```text
Android System WebView
Google Chrome
```

This helps maintain compatibility with modern web functionality including:

- JavaScript
- WebRTC
- microphone capture
- media playback
- modern browser APIs

---

## Testing

Before production release, test the app on multiple Android devices.

Recommended tests:

```text
App launches successfully

Website loads correctly

User can navigate lessons

Arabic fonts render correctly

Audio playback works

Microphone permission prompt appears

Microphone recording works

Reading feature receives microphone audio

Android back button works

Login/session persists

App handles screen rotation

App works on phones

App works on tablets

External links open correctly

Offline page appears without internet

Website updates appear without reinstalling APK
```

---

## Google Play

For Google Play deployment, create a signed release version.

A production release should use:

```text
Android App Bundle (.aab)
```

rather than distributing the debug APK.

Before publishing, configure:

- Production signing key
- Release build
- Application icon
- Feature graphic
- Screenshots
- Privacy policy
- Data safety declaration
- Application description
- Content rating
- Target audience
- Microphone permission explanation
- Google Play App Bundle

---

## Production Signing

Do not commit production signing keys or passwords to GitHub.

Files such as the following should remain private:

```text
*.jks
*.keystore
keystore.properties
local.properties
```

Recommended `.gitignore` entries:

```gitignore
.gradle/
.idea/
local.properties
*.iml
build/
app/build/
captures/
.externalNativeBuild/
.cxx/

*.jks
*.keystore
keystore.properties
```

---

## Development Architecture

The recommended architecture is:

```text
Cloudflare-hosted Web App
            +
     Native Android Shell
```

This keeps the Android application small while allowing the core Arabic Reading Coach platform to evolve independently.

---

## Future Improvements

Possible future native Android features include:

- Custom splash screen
- Native push notifications
- Offline lesson downloads
- Native audio recording
- Background audio
- Deep links
- Google authentication
- Native account authentication
- Firebase Cloud Messaging
- Google Play Billing
- App update notifications
- Tablet-specific layouts
- Android share functionality
- Download management
- Native pronunciation engine integration

---

## Development

The Android application and Arabic Reading Coach platform are currently under active development and testing.

The application should be thoroughly tested before public production use, particularly features involving:

- microphone access
- child users
- audio recording
- speech recognition
- account authentication
- data storage

---

## Related Platform

Arabic Reading Coach:

https://arabic-reading.nafishaider.com/

---

## License

This project is open source and licensed under the MIT License.
