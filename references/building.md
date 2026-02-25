# Building and Running

## Emulator or device

- **Android:** One emulator or one physical device must be running. Otherwise Skip does not know where to launch. Set `ANDROID_SERIAL` in the project `.xcconfig` to pin a device/emulator; `adb devices` lists identifiers.
- **Emulator:** `skip android emulator create` then `skip android emulator launch`, or use Android Studio Device Manager.
- **Device:** Enable USB debugging; pair device with the machine.

## Dual-platform app (single Xcode project)

- Building from Xcode builds iOS and runs the SkipStone plugin; it also builds and launches the Android app when one emulator/device is available.
- **iOS-only run:** In `AppName.xcconfig` set `SKIP_ACTION = build` (Android built but not run) or `SKIP_ACTION = none` (skip Android build). Do not leave `SKIP_ACTION = none` long-term or Android issues can accumulate.
- **Xcode Previews:** Incompatibility with Skip; use workaround `Editor > Canvas > Use Legacy Previews Execution`.

## Frameworks (library targets)

- Building a framework in Xcode does **not** run the Android compiler. To trigger an Android build: run the module’s **unit tests** with **macOS** as destination, or use `skip export`. Testing against the iOS destination does not run Android tests.

## Performance

- Use a **Release** build when evaluating real-world Android performance; Debug can differ significantly.

## Export

- `skip export` builds and exports artifacts (e.g. .apk, .ipa, .aar). Options: `--debug`, `--release`, `--module`, `--dir`, `--ios`/`--no-ios`, `--android`/`--no-android`.
