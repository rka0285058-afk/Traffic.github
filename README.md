# NCR Traffic (Simulated) - Android

Shows **simulated** traffic on 14 major Delhi NCR corridors (NH-48, Ring Road, Outer Ring Road, DND Flyway,
Noida-Greater Noida Expressway, NH-9, Mathura Road, Golf Course Road, Sohna Road, etc.).

- No API key, no account, no billing. Base map is OpenStreetMap (needs internet for map tiles only).
- Congestion follows a typical Delhi daily pattern (peaks around 9:30 and 18:30) with live random variation every 3 s.
- Slider lets you preview any hour of the day; "Now" returns to the real IST clock.
- Tap a road to see its simulated status and speed.
- Chips jump to All NCR, Delhi, Gurugram, Noida, Ghaziabad, Faridabad.

## Run
1. Open this folder in Android Studio (Koala or newer) and let Gradle sync.
2. Run on an emulator or phone (Android 8.0+).
3. APK: Build > Build Bundle(s) / APK(s) > Build APK(s).

## Customising
Edit `RoadData.roads` in `TrafficSim.kt` to add roads (list of lat/lon points, free-flow speed, jam bias).
`TrafficSim.baseLoad()` controls the daily pattern. To use real data later, replace `TrafficSim.step()`
with values from a traffic API.

## Get an APK without installing Android Studio
1. Create a free GitHub repository and upload this folder's contents (keep the `.github` folder).
2. Open the repository's **Actions** tab, run **Build APK** (it also runs on every push).
3. When it finishes (about 5 minutes), download `NCR-Traffic-Simulated-apk` from the run page and unzip it.
4. Share `app-debug.apk`. On the phone, allow "Install unknown apps" for the app you open it from.

The debug APK is signed with a debug key, which is fine for sharing and testing but not for the Play Store.
