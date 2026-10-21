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

- Read-only Health Connect: steps, distance, floors, sleep, heart rate, resting HR, exercise, plus history and background read. A test (`app`) checks that the manifest has no WRITE permissions.
- Analytics events never carry health values (`core/analytics/.../AnalyticsEvent.kt` is the full list).
- **TODO:** a Settings → "Share anonymous usage stats" switch that stops Analytics and Crashlytics. The consent flag exists in `core:datastore`, but the Settings screen is milestone 2.
- **TODO:** remove the advertising ID permission (`com.google.android.gms.permission.AD_ID`) that Firebase merges in, as Recover does.
- **TODO:** keep health-derived data out of cloud backup. The app has `allowBackup="true"`, and the Room snapshots hold daily totals. Exclude the database, or disable backup.
- **TODO:** set Firebase Analytics data retention to 14 months in the Firebase console.

## Preview locally

```sh
python3 -m http.server 8000   # then open http://localhost:8000
```
