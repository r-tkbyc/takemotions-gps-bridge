# TakeMotions GPS Bridge

A small Android helper that provides your phone's GPS location to **TakeMotions apps running in Even Hub** (the Even
Realities companion).

On Android, the Even Hub in-app browser can't read GPS directly, so apps that need your location (such as navigation)
rely on this bridge. **iOS does not need it** — those apps work without this bridge.

## How it works

While running, the bridge serves your latest GPS fix at `http://127.0.0.1:8765/gps`, reachable only from your own phone.
The TakeMotions app reads it from there.

## Privacy

- Your location is served **only to localhost on your own device** — it is never sent anywhere and never stored.
- ⚠️ While the bridge is running, **any app on your device can read your GPS position via localhost.** Start it only 
when you are actively using a TakeMotions app, and stop it when you are done.
- It **auto-stops** after the time you choose (default 3 hours).
- The app requests only the **Location** permission.

## Install

1. Download the latest **`gps-bridge-x.y.apk`** from the [Releases](../../releases) page.
2. Open the downloaded file. Android will ask permission to install from this source — allow it for your browser or
Files app.
3. Install and open **GPS Bridge**.

## Use

1. Open **GPS Bridge** and tap **Start** (grant Location when asked).
2. Open your TakeMotions app in Even Hub — it now receives your real location.
3. Tap **Stop** when you are done (or let it auto-stop).

### Screen-off / pocket use
For navigation with the screen off, set the app's **Battery** to **Unrestricted** (tap *Open app settings* → Battery).
The exact wording varies by Android version (Battery saver / Battery optimization / Background restriction).

## Settings

- **GPS update interval** — how often the bridge reads GPS (default 2 s).
- **Auto-stop** — stops automatically after 1 / 3 / 6 hours, or off (default 3 h).

---

Made by **TakeMotions** · [@r_tkbyc](https://x.com/r_tkbyc)