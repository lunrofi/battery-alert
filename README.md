# Battery Alert

![Icon](icon.png)

**Battery Alert** warns you before your phone dies. When your battery hits **1%** and you are not charging, it shows a full-screen pop-up, plays a sound, and vibrates — once per low-battery episode.

## Features
- Triggers at exactly 1% battery, only when not charging
- Full-screen red pop-up, even on the lock screen
- Normal notification sound + vibration (no alarm)
- Warns only once per 1% episode (no repeat spam)
- Stops automatically when you plug in
- Foreground service, so it keeps running in the background
- Auto-starts after reboot
- Modern dark UI, English interface

## How it works
1. Install the APK from Releases.
2. Open **Battery Alert**.
3. Tap **Start Protection**.
4. Allow notifications and "Display over other apps" when asked.
5. For best reliability, exclude the app from battery optimization.

When the battery reaches 1%, you will see:

> **BATTERY 1%!**
> Your phone is about to shut down. Plug in the charger now!

Tap **OK** to dismiss that pop-up — it will come back every 20 seconds until you charge.

## Permissions
- `FOREGROUND_SERVICE` / `FOREGROUND_SERVICE_SPECIAL_USE` — keep the monitor running
- `POST_NOTIFICATIONS` — show the alarm notification
- `VIBRATE` — vibration alert
- `SYSTEM_ALERT_WINDOW` — show the pop-up over other apps and the lock screen
- `RECEIVE_BOOT_COMPLETED` — restart protection after reboot
- `WAKE_LOCK` — wake the screen for the alert

No data is collected, no account is needed, nothing leaves your phone.

## Technical details
- Package: `com.bmo.sarjuyari`
- Version: 1.2 (versionCode 3)
- Min SDK: 26 (Android 8.0+)
- Target SDK: 34 (Android 14)
- Built with aapt2 + d8, signed, zipaligned
- Source layout: `MainActivity` (UI), `BatteryService` (foreground monitor, `ACTION_BATTERY_CHANGED`), `AlertActivity` (full-screen warning), `BootReceiver` (auto-start)

## Download
Get the APK from the **Releases** page: `battery-alert.apk`

## Screenshots / behavior
- Main screen: dark modern UI with live battery percentage
- Alert screen: full-screen red warning with big "BATTERY 1%!" text
