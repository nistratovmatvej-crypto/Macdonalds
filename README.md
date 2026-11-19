# McDonald's 2026 — Android + Web

An offline-first, multi-page website concept packaged as an Android WebView app.

## Build APK
Push to `main` or run **Actions → Android APK → Run workflow**.
The workflow extracts the bundled website source, installs Android SDK 35, builds
`app-debug.apk`, verifies the output, and uploads it as a GitHub Actions artifact.

## Local build
Requires JDK 17, Android SDK platform 35, Build Tools 35.0.0, and Gradle 8.9:
```bash
mkdir -p app/src/main/assets/www
base64 -d website-source.tar.xz.b64 | tar -xJf - -C app/src/main/assets/www
gradle assembleDebug
``

APK output: `app/build/outputs/apk/debug/app-debug.apk`.

The website is stored as a compressed text archive so the repository remains compact;
the workflow expands the original individual HTML pages and shared assets at build time.
The app itself loads only local assets. Cart and theme use browser localStorage.

This is an unofficial personal-use concept. Menu, prices, nutrition and location data
are illustrative; there is no real ordering, payment, geolocation or backend.
