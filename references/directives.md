# Compiler Directives and Platform Customization

## #if os(Android) / #if !os(Android)

Use for platform-specific code paths. Only the matching block is compiled for each platform.

```swift
#if os(Android)
print("Android")
#else
print("iOS")
#endif
```

Works in SwiftUI modifier chains:

```swift
Text("Hello")
    #if os(Android)
    .italic()
    #else
    .bold()
    #endif
```

## #if SKIP

Code inside `#if SKIP` is **transpiled** to Kotlin (excluded from iOS build). It can **call Kotlin and Java API** directly. Skip bridges non-private `SKIP` code so compiled Swift (Fuse) can call it.

```swift
#if SKIP
func androidOnly() -> String {
    return java.util.Locale.getDefault().getDisplayName()
}
#endif
```

- In **Skip Lite**, all Swift is transpiled, so `#if SKIP` and `#if os(Android)` are effectively equivalent for Android-only code.
- In **Skip Fuse**, use `#if os(Android)` to choose the Android path and `#if SKIP` to define or call code that must be transpiled (e.g. to use Kotlin/Java APIs).

## Calling Kotlin/Java from Swift

Inside `#if SKIP` blocks write **Swift syntax**; the transpiler maps it to Kotlin. Differences when pasting Kotlin:

- Named params: Kotlin `=`, Swift `:`.
- Closures: Kotlin `->`, Swift `in`.
- Package import: use `import com.xyz.__` (Swift does not allow `.*`).

Types passed in/out of `#if SKIP` functions may need to be **bridged**. Many types support bridging; custom types can be annotated. Use `.kotlin(nocopy:)` when passing Skip types (e.g. Array) to Kotlin API that expects standard Kotlin types (e.g. List).

## Kotlin files

You can add pure Kotlin files to the Xcode project; they are included in the Android build. Use for larger Android-only logic instead of embedding in `#if SKIP`.

## Unsupported iOS API

Use `#if os(Android)` (or `#if SKIP`) to exclude unsupported iOS API from the Android build and provide an Android alternative (different API, or Kotlin/Java implementation in `#if SKIP`). Never compromise the iOS app; always keep iOS code path intact.
