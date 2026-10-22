# CCTV Jakarta Android

CCTV Jakarta APK distribution repository. This repository contains installation instructions and release information, not the application source code.

## Download

Download APKs from the [Releases page](https://github.com/x00rb/CCTV-Jakarta-APP/releases). Starting with version 1.0.20, releases use the architecture-specific filenames listed below.

## Installation

Install one APK:

1. Open the Releases page and select a release.
2. Download one matching APK from Assets: `CCTV-Jakarta-arm64-v8a.apk` for most current phones, `CCTV-Jakarta-armeabi-v7a.apk` for older 32-bit ARM devices, or `CCTV-Jakarta-x86_64.apk` for 64-bit Intel devices and emulators. These are independently installable APKs; do not install all three. No universal or 32-bit x86 APK is provided.
3. Open the APK. If Android asks, allow installation from the browser or file manager you used.
4. Follow Android's installation prompts.

To update without removing application data, the APK must have the same application ID and signing identity as the installed app, and a higher versionCode. Do not uninstall the app to resolve a signing mismatch without first backing up any data you need.

## Update metadata

The `latest.json` file will be published after the first APK is available in Releases. It will contain `versionCode`, `versionName`, `releaseUrl`, and `notes`. The publisher updates this metadata only after uploading the APK and publishing its release.

Android builds starting with 1.0.17 include automatic update checks once per day and a manual **Check for updates** action on the profile screen. Automatic failures are silent; manual checks report failures. Choosing **Later** dismisses that version's automatic notification. A manual check can still show it.

The app reads:

```text
https://raw.githubusercontent.com/x00rb/CCTV-Jakarta-APP/main/latest.json
```

To publish an update:

1. Build and verify all three ABI APKs. They must share the same version and release signing identity, and each must contain native libraries only for its named ABI.
2. Create a GitHub Release in this repository, attach all three APKs, and publish the release.
3. Create or update `latest.json` with the APK's integer `versionCode`, its `versionName`, the published GitHub `releaseUrl`, and release `notes` as a string.
4. Commit and push the metadata to `main` only after verifying all three APK downloads work.

The app compares versionCode, not versionName. Its **Download update** button opens the release page in a browser; Android asks the user to approve APK installation. Missing metadata, network failures, and invalid metadata never block normal app use.

Local release builds and GitHub Actions use the same release signing key. Debug APKs use a different signing identity and cannot update a release-signed installation in place. Changing signing identity normally requires reinstalling the app.
