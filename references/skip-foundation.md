# SkipFoundation

SkipFoundation reimplements Foundation for Kotlin on Android so that transpiled Swift can use Foundation-style API. It is part of the core Skip frameworks; you do not import it directly—`import Foundation` is translated to the Skip Foundation implementation on Android.

## Scope

SkipFoundation supports many common Foundation APIs (dates, data, encoding, URLs, file manager, etc.) and parts of CryptoKit. Not all of Foundation is implemented. If an API is missing you can: use only supported API, call Kotlin/Java from `#if SKIP` blocks, or contribute to SkipFoundation.

## Dependencies

Depends on the skip transpiler plugin and SkipLib. Pulled in automatically when using Skip Lite or the relevant Skip packages.

## .kotlin() and KotlinConverting

When a SkipFoundation type wraps a Kotlin/Java type, it often conforms to `KotlinConverting<T>` and provides `.kotlin(nocopy:)` so you can pass it to Kotlin/Java API. A constructor taking the Kotlin type is usually provided for the reverse conversion.

## Status

Support is documented in the SkipFoundation repo (Foundation Support table). Use `#if !os(Android)` / `#if os(Android)` to use full Foundation on iOS and the supported subset (or Kotlin alternatives) on Android.
