# CCTV Jakarta Android

CCTV Jakarta APK distribution repository. This repository contains installation instructions and release information, not the application source code.

## Download

No APK has been published in this repository yet. APK downloads will be attached to releases on the [Releases page](https://github.com/x00rb/CCTV-Jakarta-APP/releases).

## Installation

Once an APK is available:

1. Open the Releases page and select a release.
2. Download the `.apk` file from Assets.
3. Open the APK. If Android asks, allow installation from the browser or file manager you used.
4. Follow Android's installation prompts.

To update without removing application data, the APK must have the same application ID and signing identity as the installed app, and a higher versionCode. Do not uninstall the app to resolve a signing mismatch without first backing up any data you need.

## Update metadata

The `latest.json` file will be published after the first APK is available in Releases. It will contain `versionCode`, `versionName`, `releaseUrl`, and `notes`. The publisher updates this metadata only after uploading the APK and publishing its release.

This repository does not enable update checks in the app. That feature requires changes to the Android application.
