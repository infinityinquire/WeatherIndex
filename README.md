# WeatherIndex (APK)

WeatherIndex is a small Android app (APK) that shows current weather information for your location — temperature, humidity, and a short description of conditions (sunny, cloudy, rainy, etc.). This repository contains the APK build for direct installation on Android devices.

> If you expected source code rather than an APK, check the repository for a `src/` or `app/` folder or ask the maintainer for the build files. This README focuses on installing and using the APK.

## What the app does

- Shows current temperature for your location
- Displays relative humidity
- Shows a short human-readable weather condition (example: "Light rain")
- Uses the device location to provide local weather

## APK download

If an APK file is included in this repository (for example `app-release.apk` or under `releases/`), download that file to your Android device or to your computer for sideloading.

If no APK is present here, check the repository's Releases page (https://github.com/infinityinquire/WeatherIndex/releases) or contact the maintainer.

## Install (two common ways)

1) Install directly on the device
- On Android 8+ go to Settings → Apps & notifications → Special app access → Install unknown apps and allow your browser or file manager to install APKs. (Exact menu names vary by device/Android version.)
- Open the APK file in your device file manager and tap Install.

2) Install from a computer using ADB
- Enable Developer Options and USB debugging on your phone.
- Connect the device to your computer via USB.
- Run:

  adb install -r path/to/app-release.apk

  The `-r` flag reinstalls and keeps app data if the app is already installed.

## Permissions

WeatherIndex requires:
- ACCESS_FINE_LOCATION or ACCESS_COARSE_LOCATION — to get your current location and provide local weather.
- INTERNET — to fetch weather data from the network.

The app will request these at runtime (Android 6.0+) when needed.

## Verifying APK safety

Before installing an APK from a repository, consider verifying its integrity:

- Check the file size and the SHA-256 checksum if the maintainer publishes it. Generate a checksum locally:

  sha256sum app-release.apk

- Only install APKs from sources you trust.

## Updating the app

- If a newer APK is released here or in Releases, download it and either install it over the old version (same signing key required) or uninstall the old version and install the new APK.

## Troubleshooting

- "App won’t install" — Make sure you allowed installs from unknown sources or use ADB.
- "App crashes on startup" — Check Logcat while reproducing the crash: `adb logcat` and look for stack traces from the app package.
- Location not found — Ensure location services are enabled and the app has location permission.

## Reporting issues or feedback

Open a GitHub issue in this repository describing:
- Device model and Android version
- Exact APK file name and build (if known)
- Steps to reproduce the problem
- Any relevant logs (Logcat)

## Contributing

If you'd like to contribute source code or a new build, please open a Pull Request with instructions to build the APK (Gradle commands, dependencies, and Android SDK requirements).

## License

If the project includes a LICENSE file, that controls distribution. If there's no license file, ask the maintainer before redistributing the APK.
