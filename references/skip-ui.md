# SkipUI

SkipUI reimplements SwiftUI for Kotlin on Android using Jetpack Compose. Skip Lite uses it directly; Skip Fuse uses it via SkipFuseUI.

## Setup (Package.swift)

```swift
.package(url: "https://source.skip.dev/skip-ui.git", from: "1.0.0"),
// ...
.product(name: "SkipUI", package: "skip-ui")
```

For Fuse UI use SkipFuseUI product instead.

## Supported SwiftUI

SkipUI supports a large subset of SwiftUI: state flow, declarative syntax, and many components and modifiers. Not every SwiftUI API is implemented. Check the official SkipUI module docs for the full “Supported SwiftUI” list. If something is missing you can: use only supported components, embed Compose via `ComposeView`, or contribute to SkipUI.

## ComposeView (embed Compose in SwiftUI)

Android-only view to embed Jetpack Compose in the SwiftUI tree.

**Skip Fuse:** Define a `ContentComposer` in a `#if SKIP` block (with a `@Composable func Compose(context: ComposeContext)`), then use `ComposeView { YourComposer(...) }` inside an `#if os(Android)` branch in your SwiftUI view.

**Skip Lite:** Similar; the composer is transpiled Kotlin.

## SwiftUI visibility (Fuse)

Use **default or public** visibility for Views and their SwiftUI properties so Skip can access them on Android. Private is fine for non-SwiftUI members.

## @Observable and Compose

For `@Observable` models that drive Compose UI (e.g. custom Compose screens), you may need `import SkipFuse` in the Swift file and a SwiftPM dependency on SkipModel; see app-development docs. For normal SwiftUI views, SkipFuseUI/SkipUI handle this.

## Components

See `references/components-index.md` for the list of component topics; use the specific `references/component-*.md` when available (e.g. `references/component-button.md`, `references/component-list.md`).
