# Skip CLI

Install: `brew install skiptools/skip/skip` (macOS/Linux/WSL2). Full app projects require macOS.

## Main commands

| Command | Purpose |
|---------|---------|
| `skip version` | Print Skip version |
| `skip doctor` | Evaluate and diagnose development environment |
| `skip checkup` | Full system check (creates and builds sample project); use after install |
| `skip upgrade` | Upgrade to latest Skip |
| `skip create` | Create new project **interactively** (prompts for App/Library, Fuse/Lite, name, bundle id, etc.) |
| `skip init` | Initialize new project **non-interactively**; requires flags |
| `skip verify` | Verify Skip project (structure, contents); use `--fix` to attempt fixes |
| `skip icon` | Create/manage app icons (resize for Darwin and Android) |
| `skip export` | Export Gradle project and built artifacts (.aar, .apk, .ipa) |
| `skip devices` | List connected devices and emulators/simulators |
| `skip test` | Run parity tests and generate reports |

## skip init examples

- Native app: `skip init --native-app --appid=com.example.AppName app-folder AppName`
- Transpiled app: `skip init --transpiled-app --appid=com.example.AppName app-folder AppName`
- Native library: `skip init --native-model lib-folder ModuleName`
- Transpiled library: `skip init --transpiled-model lib-folder ModuleName`

Common options: `--dir`, `--no-build`, `--no-test`, `--open-xcode`, `--open-gradle`, `--apk`, `--ipa`.

## skip android subcommands

- `skip android build` — Build native project for Android
- `skip android run` — Run on device/emulator
- `skip android test` — Test on device/emulator
- `skip android sdk list` / `skip android sdk install` — Swift Android SDK
- `skip android emulator create` / `skip android emulator list` / `skip android emulator launch` — Emulator management
- `skip android toolchain` — Swift Android Host Toolchain

## skip verify

Run in project root. Options: `--project`, `--free`, `--fastlane`, `--fail-fast`, `--fix`.

## skip export

Build and export; options include `--debug`, `--release`, `--module ModuleName`, `--dir`, `--ios`/`--no-ios`, `--android`/`--no-android`.

## Tool paths (optional)

Many commands accept `--xcodebuild`, `--swift`, `--gradle`, `--adb`, `--emulator`, `--android-home` to override tool locations.
