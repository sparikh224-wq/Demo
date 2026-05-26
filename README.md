# GoWingo — Delivery Demo

A small, interactive 2-page ecommerce demo for the **GoWingo** drone-delivery
startup (a JK Aerotech venture). Browse cold drinks, add to cart, and place an
order with a drone-delivery confirmation. Built in the GoWingo brand colours
(cyan `#29B6D8` + black).

The whole app is a single static file: `www/index.html` (no build step, no
dependencies). It's also a PWA, so it can be installed to a phone home screen
and runs fullscreen like a native app.

## 1. Run it in a browser (fastest — great for the video)

Just open the file:

```
www/index.html
```

Tip: for the best "phone" look, open your browser's device/responsive mode
(e.g. Chrome DevTools → toggle device toolbar) and pick a phone size.

## 2. Install it as an app on your phone (PWA)

PWA install needs the app served over http(s) (not `file://`). Serve it:

```bash
npx --yes serve www
```

Then open the printed URL on your phone (same Wi-Fi), and use the browser's
**Add to Home Screen**. It launches fullscreen with the GoWingo icon — looks
identical to a native app on camera.

## 3. Build a real Android APK (run on your own machine)

> This must be done on your own machine, not in the cloud sandbox — the cloud
> environment blocks Google's servers (`dl.google.com`), which the Android SDK
> and Android Gradle Plugin are downloaded from.

Requirements: Node.js, JDK 17+, and Android Studio (or the Android SDK +
`ANDROID_HOME` set).

```bash
# one-time setup: installs Capacitor, adds the Android project
npm run apk:setup

# build a debug APK
npm run apk:build
```

The APK lands at:

```
android/app/build/outputs/apk/debug/app-debug.apk
```

Copy that to a phone and install it (enable "install from unknown sources").

App id: `com.gowingo.demo` · App name: **GoWingo**
