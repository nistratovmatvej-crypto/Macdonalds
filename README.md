# McDonald's 2026 — Android + Web

An offline-first, multi-page website concept packaged as an Android WebView app.

## Pages
- `website/index.html` — home
- `website/menu.html` — searchable/filterable menu
- `website/product.html` — product detail
- `website/about.html` — brand story
- `website/locations.html` — demo locations
- `website/careers.html` — careers
- `website/app.html` — mobile app showcase
- `website/contacts.html` — contact form and FAQ
- `website/styles.css`, `website/app.js` — shared design system and interactions

## Build APK
Every push to `main` starts **Actions → Android APK**. The workflow:
1. Checks out this repository.
2. Installs JDK 17 and Android SDK 35.
3. Copies the complete `website/` directory into Android app assets.
4. Builds the debug APK with Gradle 8.9.
5. Verifies the APK exists and uploads it as the `McDonalds-2026-debug-apk` artifact.

To download: open the repository's **Actions** tab, select the latest successful **Android APK** run, and download its artifact.

## Local build
Requires JDK 17, Android SDK platform 35, Build Tools 35.0.0 and Gradle 8.9:
```bash
gradle --no-daemon assembleDebug
```
APK: `app/build/outputs/apk/debug/app-debug.apk`.

The Android app loads local files only. Cart and theme preferences use WebView localStorage. The location map, restaurants, prices and nutrition are illustrative; the contact form is a front-end demo. This is an unofficial personal-use concept.
