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

Android builds starting with 1.0.17 include automatic update checks once per day and a manual **Check for updates** action on the profile screen. Automatic failures are silent; manual checks report failures. Choosing **Later** dismisses that version's automatic notification. A manual check can still show it.

The app reads:

```text
https://raw.githubusercontent.com/x00rb/CCTV-Jakarta-APP/main/latest.json
```

To publish an update:

1. Build and verify the APK. Keep its signing identity consistent with previously distributed APKs.
2. Create a GitHub Release in this repository, attach the APK, and publish the release.
3. Create or update `latest.json` with the APK's integer `versionCode`, its `versionName`, the published GitHub `releaseUrl`, and release `notes` as a string.
4. Commit and push the metadata to `main` only after verifying the APK download works.

The app compares versionCode, not versionName. Its **Download update** button opens the release page in a browser; Android asks the user to approve APK installation. Missing metadata, network failures, and invalid metadata never block normal app use.

The current local APK is debug-signed. GitHub Actions can use a different debug key, so do not mix locally built and CI-built APKs as interchangeable updates. Establish a backed-up release signing key before broad distribution; changing signing identity normally requires reinstalling the app.
