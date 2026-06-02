# MoneyFlow Project

## Overview

MoneyFlow is an Android application (package `com.example.moneyflowai`) built with Android SDK 36, targeting Android API 36. It uses Firebase (Auth, Firestore, Storage), Room for local persistence, and common AndroidX libraries. The project includes `google-services.json` and is configured with the Firebase BOM (`34.12.0`).

## Project metadata

- Application ID / namespace: `com.example.moneyflowai`
- Compile SDK: 36
- Min SDK: 24
- Target SDK: 36
- Version: 1.0 (versionCode 1)
- Java compatibility: Java 11

## Key dependencies (high level)

- AndroidX AppCompat, Material, ConstraintLayout
- Android Navigation component
- Lifecycle ViewModel / LiveData
- MPAndroidChart
- SwipeRefreshLayout
- Firebase Auth / Firestore / Storage (via Firebase BOM)
- Biometric (androidx.biometric)
- Lottie animations
- Glide (image loading)
- Room (local database)

See `app/build.gradle.kts` for the exact versions and the `libs.versions.toml` file for centralized dependency versions.

## Prerequisites

- JDK 11
- Android SDK with API 36 installed
- Android Studio (recommended) or Gradle wrapper
- On Windows: use `gradlew.bat`

## Build & Run (CLI)

From the project root on Windows:

```bash
.\gradlew.bat assembleDebug
.\gradlew.bat installDebug
```

Or open the project in Android Studio and run the `app` module.

To install the debug APK manually (after build):

```bash
adb install -r app\build\outputs\apk\debug\app-debug.apk
```

## Tests

Run unit tests:

```bash
.\gradlew.bat test
```

Run instrumentation tests on a connected device/emulator:

```bash
.\gradlew.bat connectedAndroidTest
```

## Firebase

The project contains `app/google-services.json` for Firebase configuration. Ensure the SHA-1/SHA-256 keys for your debug/release signing are configured in the Firebase console if you use authentication features.

## Notes & Troubleshooting

- Gradle properties increase JVM memory and disable automatic SDK downloads; ensure API 36 is installed locally.
- If you see SDK download errors, either enable SDK downloads in `gradle.properties` or install API 36 via the SDK Manager.
- If build fails due to annotation processors, ensure annotation processing is enabled in Android Studio settings.

## Project structure (top-level)

- `app/` — Android application module (source, resources, Gradle config)
- `gradle/`, `build.gradle.kts`, `settings.gradle.kts`, `gradle.properties` — build configuration

## Contributing

Create issues or PRs; follow existing code style. If adding dependencies, prefer centralized versions in the `libs.versions.toml` file.

## License

Add an appropriate license file as needed.
