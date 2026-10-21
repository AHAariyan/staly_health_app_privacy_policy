# Statly · privacy policy

This is the public privacy policy for the Statly Android app (`com.statly.app`), served by GitHub Pages:
**https://ahaariyan.github.io/staly_health_app_privacy_policy/**

That URL goes in three places:
- Play Console → App content → Privacy policy.
- The **Health apps declaration** in Play Console.
- The app itself: Settings, and Health Connect's permission screen through `PermissionsRationaleActivity`.

Google checks the page against the app's permissions and the Data safety answers, so it is kept accurate to the code, not to intentions.

## Files

| File | Purpose |
|---|---|
| `index.html` | The whole policy. No build step, no framework. |
| `favicon-32.png`, `apple-touch-icon.png` | Made from the Calm stones app icon. |
| `.nojekyll` | Serves the files as they are. |

## When to update it

Update this page **in the same change** as anything that changes:
- which Health Connect types are read;
- what leaves the device;
- a new SDK;
- a retention change.

Update the effective date at the same time, and update the Play Data safety form to match.

## Claims the code must keep true

Checked against the app on 21 October 2026. Items marked **TODO** must be done in the app before release.

- The Health Connect rationale screen links this policy (`ScreensTest.privacyNote_opensThePrivacyPolicy`).
- Read-only Health Connect: steps, distance, floors, sleep, heart rate, resting HR, exercise, plus history and background read. A test (`app`) checks that the manifest has no WRITE permissions.
- Analytics events never carry health values (`core/analytics/.../AnalyticsEvent.kt` is the full list).
- Opting out stops Analytics and Crashlytics and resets the app-instance id, at startup and on change (`AnalyticsConsentTest`). **TODO:** the Settings switch UI itself (milestone 2); it calls `AnalyticsConsent.set(enabled)`.
- No advertising ID or ad-services permissions in the merged manifest (`ManifestTest.noAdvertisingId`).
- No cloud backup or device transfer of app data: `allowBackup="false"` plus `data_extraction_rules.xml` (`ManifestTest.healthDerivedData_isNotBackedUpOrTransferred`).
- **TODO:** set Firebase Analytics data retention to 14 months in the Firebase console.

## Preview locally

```sh
python3 -m http.server 8000   # then open http://localhost:8000
```
