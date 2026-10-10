# LaterLinks - Android APK project

A bookmarking app (save links for later) wrapped as a native Android app
with Capacitor. Same features as the web version: save/search/tag links,
import/export JSON, Google Drive backup & auto-sync.

## Build the APK (no Android Studio needed)

1. Create a new repository on github.com and upload **all these files**
   (keep the folder structure, including `.github/workflows/build-apk.yml`).
2. Go to the **Actions** tab in your repo -> "Build APK" -> **Run workflow**.
3. Wait ~5 minutes, then open the completed run and download the
   **LaterLinks-APK** artifact. That's your installable `.apk`.

## Install on your phone

- Copy `app-debug.apk` to the phone and tap it.
- You may need to allow "Install from unknown sources" for your file manager.
- Debug APKs are signed with a debug key, so Android may show a
  " Play Protect doesn't recognize this developer" warning - tap
  "Install anyway".

## Google Drive sync

Open the app, tap the cloud icon, and paste your own Google OAuth
Web Client ID (the app includes step-by-step instructions).
The Client ID must have your app's origin authorized.

> NOTE: Google blocks its sign-in page inside app WebViews.
> For Drive sync to work inside the APK, use the
> `@capacitor-community/google-auth` plugin (native sign-in popup)
> and pass the returned access token to the app's sync code,
> instead of the web-based sign-in button.

## Build locally instead (optional)

1. Install Android Studio (includes SDK + Gradle).
2. `npm install && npx cap add android && npx cap sync android`
3. Open the `android/` folder in Android Studio -> Build -> Build APK(s).
