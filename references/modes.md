# Skip Fuse vs Skip Lite

Mode is set per Swift module in `Skip/skip.yml`:

```yaml
skip:
  mode: 'native'   # Skip Fuse
  # or
  mode: 'transpiled'   # Skip Lite (default if omitted)
```

A single app can mix native and transpiled modules; use bridging to interface between them.

## Skip Fuse (native)

- Swift is **compiled natively** for Android (Swift SDK for Android).
- **Pros:** Full Swift language; faithful runtime; full stdlib/Foundation; thousands of third-party Swift packages; C/C++ integration; high performance, lower memory watermark.
- **Cons:** Larger Android app (~60 MB added); Kotlin/Java interaction requires **bridging**; debugging native on Android is harder; slower Android builds; if you eject, only iOS app remains.
- **Package.swift:** Native modules typically depend on SkipFuse, SkipModel (model); SkipFuseUI (UI).

## Skip Lite (transpiled)

- Swift is **transpiled to Kotlin** for Android.
- **Pros:** Direct Kotlin/Java API calls (no bridging); transparent, readable Kotlin output; ejectable (you keep both Swift and Kotlin codebases); smaller app; faster Android build iteration.
- **Cons:** Some Swift language features not mappable to Kotlin; different runtime behavior (e.g. GC vs deterministic deallocation); limited stdlib/Foundation vs native; fewer third-party transpiled libraries; C/C++ integration more involved.
- **Package.swift:** Transpiled modules depend on SkipModel (model); SkipUI (UI). No SkipFuse.

## Bridging (Fuse)

In Fuse, moving data between compiled Swift and Kotlin/Java requires **bridging**. Configure in `skip.yml`. Non-private code in `#if SKIP` blocks is bridged so compiled Swift can call it. See platform customization for calling Kotlin/Java from Swift (`#if SKIP`).

## Choosing mode

- **Fuse:** Recommended for most apps; full language and ecosystem; accept larger APK and bridging when needed.
- **Lite:** Good for libraries that need tight Kotlin/Java integration or minimal app size; or when ejectability matters.
