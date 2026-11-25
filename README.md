# WarRig Companion

**The Android app for your QIDI 3D printer.** Watch, control and look after your printer and QIDI BOX from your phone, with safety features that keep watching even when the app is closed.

Works with official QIDI firmware, and with WarRig firmware once it is released.

![Android](https://img.shields.io/badge/Android-8.0%2B-3DDC84?logo=android&logoColor=white)
![Version](https://img.shields.io/badge/version-1.0.0-FF8709)
![License](https://img.shields.io/badge/license-GPL--3.0-blue)

---

## Contents

- [Supported printers](#supported-printers)
- [Features](#features)
- [Download and install](#download-and-install)
- [First start](#first-start)
- [Settings explained](#settings-explained)
- [Safety](#safety)
- [Privacy and permissions](#privacy-and-permissions)
- [Troubleshooting](#troubleshooting)
- [Roadmap](#roadmap)
- [License](#license)

---

## Supported printers

WarRig Companion talks to **Moonraker**, the service that runs alongside Klipper firmware. When it connects it checks what your printer has and hides controls it doesn't have.

| Printer | Support |
| --- | --- |
| QIDI Q2 / Q2C | Full, including the QIDI BOX (main test printer) |
| QIDI Plus4, Max4 | Full, including the QIDI BOX |
| QIDI Q1 Pro, X-Plus 3, X-Max 3 | Everything except the QIDI BOX |
| Other Klipper + Moonraker printers (Voron, Sovol SV08, Elegoo Neptune 4, rooted Creality K1, Sonic Pad …) | Camera, files, temperatures, motion, alerts, stats and backup. QIDI-only buttons are hidden |
| Bambu Lab, stock Prusa, stock Creality K1, Marlin-only printers | Not supported (no Moonraker) |

> Only the QIDI Q2 has been tested so far. Reports from other printers are welcome in [Issues](../../issues).

---

## Features

### Watch
- **Live camera:** smooth MJPEG stream with pinch zoom up to 6×, pan, rotate and flip
- **Snapshots and video clips** saved to your phone
- **Picture-in-picture:** keep the camera in a small floating window
- **Picture adjustments:** brightness, contrast, saturation and more, where the camera supports them
- **Low data mode:** switch to a lighter stream, automatically when nothing is printing
- **Live print notification:** progress bar, layer and time left on your lock screen, with **Pause / Resume** and **Light** buttons
- **First-layer check:** an alert with a camera photo when the first layer is done, with an option to pause after layer 1
- **"Almost done" alert** about 10 minutes before a print finishes
- **Print alerts:** started, finished, cancelled, paused (with the reason: tangle, run-out, clog …) and errors
- **Home-screen widget** with progress, time left and temperatures

### Control
- Nozzle, bed and chamber temperatures
- Part, auxiliary and chamber fans
- **Preheat presets** for PLA, PETG, ABS/ASA and more
- Move, home and level, with step sizes and a bed up/down pad
- Speed, flow and live Z offset (babystep)
- Case light on/off
- **Skip a failed part mid-print** (exclude object) from a plate map
- Calibration tools and a visual bed mesh
- Console for advanced users, behind a beginner warning
- Emergency stop and firmware restart

### QIDI BOX
- Every slot shown in its **real spool colour**, with material and brand
- **Load, unload and eject** filament from your phone
- **Dry while you print**, kept at a safe temperature for the loaded filament
- **Auto-dry:** starts the dryer when humidity goes over your limit, for a set time
- Humidity and temperature for each BOX
- Pick which slot each colour of a print uses, matched automatically by colour and material
- Spool notes with grams left, and **low-filament warnings**
- Supports up to 4 BOXes (16 slots)

### Files
- **Share to print:** use "Share" or "Open with" in your slicer, Drive or file manager to send G-code straight to the printer
- Upload, then print with one tap
- **Search and sort** by name, date, size, print time or filament
- Slicer thumbnails, print time and filament use
- **Print queue** with an "up next" banner
- Files on a **USB drive** plugged into the printer
- **Timelapse videos:** play, download or delete

### Safety
- **Forgotten heater guard:** if heaters are on and nothing is printing, you get an alert, then they switch off. Calibration and the BOX dryer are never touched
- **Stuck print alert** when progress stops moving
- **Filament checks before printing:** warns if a slot holds the wrong material or doesn't have enough filament left
- **Chamber limit for PLA:** keeps the chamber at 45 °C or less with PLA loaded
- **Motion lock:** blocks homing, jogging and calibration during a print; filament changes still work while paused
- **Control PIN (guest mode):** others can watch, only you can control. Emergency stop always works

### Smart extras
- **Print statistics:** hours, success rate, filament used and a 6-month chart
- **Maintenance reminders** based on print hours, for example plate, rods, nozzle and belts, with your own intervals
- **Settings backup:** copies the printer's config files to `Downloads/WarRig` on your phone. Read-only on the printer
- **Weekly backup** and **automatic timelapse download** (optional)
- **Several printers:** save, rename and switch between them, see all of them at a glance, and **find printers on your Wi-Fi** automatically
- **App icon shortcuts:** long-press the icon for Camera, QIDI BOX, Files or All printers
- **Demo mode** to try every screen without a printer. It turns off when you leave the app
- **Automatic update check** when the app opens

### Not tested yet

These are in the app and marked **NOT TESTED** until they have been tried on a real printer:

- Smart plug control (Shelly, Shelly Plus / Gen 2+, Tasmota, or a Moonraker power device): power off after a print and power cut on a heater error
- Air filter run after ABS / ASA / PC / PA prints

---

## Download and install

1. Open the [latest release](https://github.com/RuntimeRangerVS/WarRig/releases/latest) and download the `.apk` file to your phone.
2. Open it. If Android asks, allow installing apps from your browser or file manager.
3. Open **WarRig Companion**.

The app checks for new versions each time it opens and offers to download them. You can turn this off in **Settings → App**.

**Requirements:** Android 8.0 or newer, with the phone on the same network as the printer.

---

## First start

1. When the app opens, tap **Add a printer**, or **Find printers on this Wi-Fi** to search automatically.
2. Enter a name and the printer's IP address, for example `192.168.0.66`. You'll find it on the printer screen under network / Wi-Fi settings. Port `7125` is added automatically.
3. Tap the printer to connect. To skip this screen next time, tick **Connect to the last printer automatically**.
4. Optional: in **Settings → Notifications** turn on **Print alerts**, and allow notifications when Android asks.

If your Moonraker needs an API key, add it in **Settings → Printer → Connection details**. The key is kept in memory only and never saved on the phone.

---

## Settings explained

| Section | What's there |
| --- | --- |
| Printer info | Firmware, Klipper and Moonraker versions, CPU, memory, storage, network |
| App | Update check, Demo mode |
| Printer | Switch / add printers, API key, firmware restart, detected features |
| Notifications | Print alerts, keep watching in the background |
| During a print | Live notification, first-layer check, pause after first layer, almost done, after-print actions (light off, chamber heater off, BOX dryer off) |
| Safety | Heater guard, stuck print alert, PLA chamber limit, motion lock, heater-error power cut, control PIN |
| Automatic | Auto-dry, air filter, power off after print, clear-the-plate alert, light with camera, weekly backup, save timelapses, smart plug |
| Printer care | Upkeep reminders, print statistics, settings backup |

---

## Safety

- The app asks you to confirm every action that moves the printer, heats it or starts a print.
- Every start goes through a **"the build plate is clear"** check.
- The console sends G-code with **no safety checks**. Only use it if you know G-code.
- Automatic actions (heater guard, auto-dry, after-print actions, smart plug) are sent like any other command and logged under **Notifications**.
- Klipper's own thermal protection always stays in charge. The app adds to it and never replaces it.

---

## Privacy and permissions

WarRig Companion talks **only to your printer** (and smart plug, if you set one up) on your home network, plus GitHub for the update check. It has no accounts, no cloud and no tracking.

| Permission | Why |
| --- | --- |
| Internet / network state | Connect to the printer on your network |
| Notifications | Print alerts and the live progress notification |
| Foreground service | Keep watching while the app is closed (it shows its own notification and can be stopped any time) |
| Run at startup | Re-schedule local print-plan reminders only. No printer connection starts at boot |

Snapshots, clips, backups and timelapses are saved to your phone's **Pictures, Movies and Downloads** folders under `WarRig`.

---

## Troubleshooting

**Can't connect**
- Check that the phone is on the same Wi-Fi as the printer, not mobile data or a guest network.
- Check the IP address on the printer screen. Try opening `http://<printer-ip>:7125/server/info` in the phone's browser.
- If Moonraker requires an API key, enter it under **Settings → Printer → Connection details**.

**No camera picture**
- The camera only works on your home network for now (see [Roadmap](#roadmap)).
- Make sure the printer's webcam is enabled. The app tries the common stream addresses automatically.

**No alerts while the app is closed**
- Turn on **Print alerts**, and either **Keep watching in background** or **Live print notification**.
- Some phones stop background apps. Set WarRig Companion's battery use to **Unrestricted** in Android settings.

**BOX slot shows the wrong colour**
- The colour comes from the BOX (RFID or saved setting). Tap the refresh button on the BOX page, or set the spool on the printer.

---

## Roadmap

- Away-from-home access (camera and control outside your home network)
- Tested smart plug and air filter support
- More printer models confirmed
- WarRig firmware integration once released

Ideas and bug reports are welcome in [Issues](../../issues).

---

## License

Released under the **GNU General Public License v3.0**. See [LICENSE](LICENSE).

WarRig Companion is an independent project. It is not made, endorsed or supported by QIDI Technology. QIDI, Klipper and Moonraker names are used only to describe compatibility.
