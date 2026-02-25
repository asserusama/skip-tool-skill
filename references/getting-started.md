# Getting Started

## New vs existing project

- **New:** User wants to create a Skip app or library. No `Package.swift` or `Skip/skip.yml` in context, or user says "create", "new project", "get started".
- **Existing:** Project already has Skip structure (e.g. `Package.swift`, `Skip/skip.yml`, Darwin/ and Android/ folders). Infer from workspace.

## Is Skip installed?

- Check: `which skip` or `skip version`.
- If not installed: `brew install skiptools/skip/skip` (requires [Homebrew](https://brew.sh)).
- Install adds the `skip` binary and Android SDK/gradle dependencies.

## Prerequisites

- **macOS 15+** (Skip requirement).
- **Xcode** (Swift, SwiftUI, iOS builds).
- **Android Studio** (Android SDK; emulator can be used without keeping Android Studio running).
- **Homebrew** (for installing Skip).

## Environment check

Run from terminal:

```bash
skip checkup
```

This validates Skip version, macOS, Swift, Xcode, Gradle, Java, ADB, and optionally creates and builds a sample project. Use `skip checkup --verbose` for more detail. If checkup fails, suggest the FAQ and community (Slack, forums).

## Flow for a new project

1. Install Skip: `brew install skiptools/skip/skip`
2. Run `skip checkup`
3. Create project: `skip create` (interactive) or `skip init` (non-interactive)
4. During `skip create`: choose App or Library; choose **Skip Fuse** or **Skip Lite**
5. Optionally create/launch Android emulator: `skip android emulator create`, then `skip android emulator launch`

## Emulator (for running Android app)

- Create default emulator: `skip android emulator create`
- Launch: `skip android emulator launch`
- Or use Android Studio Device Manager to create and launch an emulator.
