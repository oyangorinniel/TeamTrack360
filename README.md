# TeamTrack 360 (100% Free Family & Team GPS Tracker)

A Life360-inspired Android app built with **Kotlin**, **Jetpack Compose**, **OpenStreetMap (OSMdroid)**, **Room**, **WorkManager**, and **Firebase Spark (Free Tier)**.

## Key Features
- **Google Account Sign-In** (plus built-in Local Offline Test Mode if Firebase is not linked yet).
- **Private Team / Circle Codes:** Create a circle as **Admin** or join with a 6-character code.
- **Role & Permission Controls:** Admin sees all members' live locations, GPS trails, battery levels, and GPS status. Admin can toggle per-member permissions:
  - *Can view others' live locations*
  - *Can view others' GPS trails*
  - *Can review own previous trails*
- **Offline Trail & Chat Queueing:** GPS points (recorded every 20s / 20m) and chat messages are saved locally in Room when offline and batch-uploaded automatically via WorkManager once internet returns.
- **GPS-Off Timestamp Logging:** Detects when location services are turned off on a member's phone and displays the exact timestamp to the team.
- **Live Battery & Charging Status:** Reports member battery percentage and charging state.
- **100% Free Maps:** Uses OpenStreetMap via OSMDroid (zero Google Maps billing or API keys needed).

## Connecting Free Multi-Device Sync (Firebase Spark Plan - $0/month)
1. Go to [Firebase Console](https://console.firebase.google.com/) and create a free project.
2. Add an Android app with package name: `com.teamtrack360.app` (also add your debug/release SHA-1 fingerprint for Google Sign-In).
3. Enable **Authentication -> Sign-in method -> Google**.
4. Create a **Realtime Database** (start in test mode or restrict to authenticated users).
5. Download `google-services.json` and place it inside `app/google-services.json` in your GitHub repo. GitHub Actions will automatically detect it and build a synced APK!
