# 🛟 FlySpark Support

We are happy to help you get flying. 🚁

## 1️⃣ Check the docs first

- ✨ [FlySpark F4 V2 page](FC/FlySpark-F4-V2)
- 🧠 [FlySpark F4 V1 / V2 manual & pinout](FC/FlySpark-F4-V1)
- 💾 [F4 V1 / V2 firmware + flashing guides](FC/FlySpark-F4-V1/firmware)
- ⚙️ [BLS 60A ESC settings](ESC/FlySpark-BLS-60A)
- 🟦 [H743 Pro](FC/FlySpark-H743-Pro)

## 2️⃣ Contact us

| Channel | |
|---|---|
| 🐞 GitHub issue | [Open a support request](https://github.com/flyspark015/FlySpark/issues/new/choose) |
| 💬 WhatsApp | [+91 63757 29997](https://wa.me/916375729997) |
| 📞 Phone | [+91 63757 29997](tel:+916375729997) |
| ✉️ Email | [info@flyspark.in](mailto:info@flyspark.in) |
| 🌐 Website | [flyspark.in/contact](https://flyspark.in/contact) |

## 3️⃣ What to send us (faster answers ⚡)

- Board name (e.g. *FlySpark F4 V2*) and where you bought it
- Firmware + version (e.g. *Betaflight 2026.6.2*)
- What you expected vs what happened
- Screenshot of the configurator / Mission Planner, or the CLI `diff all` / parameter file
- Photo of your wiring if it is a hardware question

## 🔧 Quick fixes

| Problem | Try this |
|---|---|
| Board not detected on USB | Use a data USB-C cable · install drivers (Betaflight App → driver install / ImpulseRC Driver Fixer) |
| Can't flash / stuck | Hold **BOOT** while plugging USB-C (DFU mode), flash again with Full chip erase |
| All 4 battery LEDs blinking | FC has no flight firmware or is in DFU — flash Betaflight / INAV / ArduPilot |
| Motors don't spin | DShot300, bidirectional DShot OFF, battery connected, props off, check Motors tab |
| Wrong battery voltage | Betaflight/INAV `vbat_scale 110`, ArduPilot `BATT_VOLT_MULT 11.0` |
| Current shows nonsense | The BLS 60A has no current sensor → set current meter OFF / `BATT_MONITOR 3` |
