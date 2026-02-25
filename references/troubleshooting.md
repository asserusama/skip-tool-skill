# Troubleshooting

## First steps

1. **Clean and reset:** Clean Xcode build (`Product` → `Clean Build Folder`), reset packages (`File` → `Packages` → `Reset Package Caches`). Restart Xcode if needed.
2. **Deeper clean:** Trash the project’s `.build` folder and Xcode’s `DerivedData` for the project if issues persist.
3. **Environment:** Run `skip checkup` (and `skip checkup --verbose` if it fails). Include `skip checkup` output when asking for help.

## Getting help

- **Slack:** Community Slack for real-time support.
- **Forums:** Skip discussion forums for questions and feedback.
- **Bugs:** Issue tracker (e.g. source.skip.dev/skip/issues). Search docs, issues, and discussions before reporting.

## Build errors

- Errors are usually shown in Swift source and in Xcode’s issue navigator. Kotlin compilation errors often include a link to the generated Kotlin source in the sidebar.
- Common causes: unsupported iOS API on Android (use compiler directives and Android fallback); cross-platform imports (see porting guide). Never assume an error means you cannot use an iOS feature; use `#if os(Android)` and provide an Android path.

## Plugin / architecture

Skip relies on Xcode 15+ and SwiftPM 5.9+ plugin support. If the plugin misbehaves, clean and reset as above; ensure Xcode and Skip are up to date.
