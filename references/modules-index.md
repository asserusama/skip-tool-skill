# Skip Modules Index

Skip provides many modules for dual-platform development. Add them as Swift package dependencies; use `Skip/skip.yml` and the skipstone plugin for your targets.

## Core / UI

- **SkipUI** — SwiftUI reimplementation for Kotlin/Android (Jetpack Compose). Used by Skip Lite directly; by Skip Fuse via SkipFuseUI. See `references/skip-ui.md`.
- **SkipFuseUI** — Native (Fuse) SwiftUI-on-Android; bridges to SkipUI/Compose.
- **SkipFoundation** — Foundation API for transpiled Swift on Android. See `references/skip-foundation.md`.
- **SkipLib** — Core transpilation support and runtime utilities.
- **SkipModel** — Model/observable support for Compose integration.
- **SkipBridge** — Bridging between Swift and Kotlin/Java (Fuse).
- **SkipFuse** — Native Swift on Android (Fuse) runtime/toolchain integration.
- **SkipUnit** — XCTest → JUnit for Android tests.

## Platform / services

- **SkipKeychain** — Keychain/secure storage.
- **SkipDevice** — Device info and capabilities.
- **SkipBluetooth**, **SkipNFC** — Bluetooth and NFC.
- **SkipAV** — Audio/video (transpiled).
- **SkipWeb** — Web view / web content.

## Data / backend

- **SkipSQL** — SQL database.
- **SkipSupabase**, **SkipFirebase** — Backend services.
- **SkipStripe** — Payments.
- **SkipXML**, **SkipZip** — Parsing and archives.

## Other

- **SkipFFI** — FFI for transpiled Kotlin and native C on Android.
- **SkipMotion** — Motion/animation.
- **SkipScript** — Scripting.
- **SkipSentry**, **SkipPostHog** — Analytics/crash reporting.
- **SkipQRCode** — QR code.
- **SkipAuthenticationServices**, **SkipAuth0** — Auth.
- **SkipMarketplace**, **SkipKit**, **SkipRevenue**, **SkipSocketIO**, **SkipNotify**, **SkipVault** — Various features.

For a given module, add the package URL (e.g. `https://source.skip.dev/skip-ui.git`) and the product name in `Package.swift`; ensure the target has the correct `mode` in `Skip/skip.yml` and the skipstone plugin.
