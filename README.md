# Nexy releases

Installers and update manifests for the Nexy apps. Source code is maintained separately.

## Install

Download from [Releases](../../releases/latest):

| Platform | File |
|---|---|
| macOS (Apple silicon) | `Nexy_<version>_darwin-aarch64.dmg` |
| Android (arm64) | `Nexy_<version>_android-arm64.apk` |

Installed apps check `latest.json` in the latest release and offer updates. On macOS the update installs and restarts the app; on Android the system installer opens for confirmation.

## Verify

- Android: the APK is signed with a certificate whose SHA-256 fingerprint is
  `9B:11:4C:F4:85:4E:0D:18:6D:FA:98:F6:27:12:1D:82:2C:32:FA:F5:A9:FE:BA:C6:A7:A7:25:B3:2B:D5:BA:0A`.
  Check with `apksigner verify --print-certs <file>.apk`.
- macOS updates: each `.app.tar.gz` has a `.sig` signature, checked by the app against this public key:
  `dW50cnVzdGVkIGNvbW1lbnQ6IG1pbmlzaWduIHB1YmxpYyBrZXk6IEQ0MjcwRUNFNDg4RURGNEQKUldSTjM0NUl6ZzRuMUNkbFJDbXMrS082emtJK0JKVkx0MythdkNzdFdJb1h6NlFuYjZKd0VXVFIK`
- `latest.json` lists the SHA-256 of each APK.

Builds are not yet notarized by Apple or published on Google Play; macOS and Android will ask for confirmation on first install.
