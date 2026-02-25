# Porting Swift Packages to Android

## Finding compatible packages

[Swift Package Index](https://swiftpackageindex.com/search?query=platform%3Aios%2Candroid) lists many packages that already build for Android. Prefer those when possible.

## Good candidates for porting

- Business logic, algorithms, data structures
- Networking, API clients, persistence
- Parsers, formatters

Harder: UIKit-only UI, HealthKit/CarPlay/Siri, other Apple-only framework integrations (possible but requires bridging to Kotlin/Java equivalents).

## Quick try

After installing Skip and the Android SDK (`skip android sdk install`), from the package directory run:

```bash
skip android build
```

If the build succeeds, the package is already Android-compatible. If not, port using the patterns below.

## Conditional imports

Use `#if canImport(ModuleName)` so code that uses an Apple-only module is only compiled when that module exists (e.g. on Darwin, not on Android):

```swift
#if canImport(EventKit)
import EventKit
extension EKEvent : Event { ... }
#endif
```

For Android you may need a separate implementation (e.g. in `#if os(Android)` or `#if SKIP`) or a stub type that conforms to the same protocol.

## Other porting issues

- **Imports:** Some types live in different modules on Android (e.g. SkipFoundation). Check the porting guide in the docs for the correct import and any re-exports.
- **Unavailable API:** Replace or wrap in `#if os(Android)` / `#if SKIP` and provide an Android implementation or alternate API.
- **Dependencies:** Add Skip packages (e.g. skip, skip-fuse, skip-model) and the skipstone plugin to `Package.swift`; add `Skip/skip.yml` with `mode: 'native'` or `'transpiled'` as needed.

When in doubt, search the docs and Skip discussions for the specific API or error.
