# SkateQuest

A Flutter app project. Right now the codebase is the stock `flutter create`
counter template: a single screen with a button that counts taps. Game
features are not implemented yet.

## What is in the repo

- `lib/main.dart` - the counter app (`MyApp`, `MyHomePage`)
- `test/widget_test.dart` - one widget test covering the counter
- Platform folders for Android, iOS, Linux, macOS, Web, and Windows
- `pubspec.yaml` - depends only on `flutter` and `cupertino_icons`;
  dev deps are `flutter_test` and `flutter_lints` (Dart SDK `^3.7.0`)

## Prerequisites

- Flutter SDK 3.47.x on the stable channel (older 3.x versions with Dart
  >= 3.7.0 may work but were not verified)
- A toolchain for the platform you want to run on:
  - Linux desktop: the packages listed in the
    [Flutter Linux setup docs](https://docs.flutter.dev/platform-integration/linux/setup)
  - Android: Android Studio + Android SDK
  - Web: Chrome (or set `CHROME_EXECUTABLE`)
  - iOS/macOS: a Mac with Xcode

## Setup

```sh
git clone <your fork url>
cd skatequest
flutter pub get
```

## Run

```sh
flutter devices            # see what is available
flutter run -d linux       # or chrome, android emulator, etc.
```

## Checks

```sh
flutter doctor
flutter analyze
flutter test
```

Verified on Fedora Linux 44 with Flutter 3.47.7 (stable), Dart 3.13.5:

- `flutter pub get`: resolves cleanly
- `flutter analyze`: no issues found
- `flutter test`: 1 test passed
- `flutter doctor`: Linux toolchain and device OK; Android SDK and Chrome
  were not installed on the verification machine, so Android and web builds
  are untested

## CI

`.github/workflows/flutter-ci.yml` runs `flutter pub get`,
`flutter analyze`, and `flutter test` on Ubuntu with Flutter 3.47.7
(stable) for every pull request and push to `main`.

## Known limitations

- No gameplay exists yet, only the template counter screen
- `pubspec.yaml` still has the placeholder description "A new Flutter
  project."
- iOS and macOS builds require macOS/Xcode and are untested
