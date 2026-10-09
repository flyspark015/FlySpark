<div align="center">

# 📶 FlySpark Bluetooth Bridge V12 — FlySpark F4 V1 / V2

[![BLE](https://img.shields.io/badge/BLE_bridge-V12-2962FF?style=for-the-badge)](#)
[![Chip](https://img.shields.io/badge/ESP32--C3-on_board-222?style=for-the-badge)](#)

[⬅️ All firmware](../README.md)

</div>

The F4 V1 and V2 have an **ESP32-C3** that links your phone to the flight controller (UART4, 115200). It is **factory
installed** — you only need this file to repair or update the Bluetooth chip.

## ✨ What V12 does

- 📱 Advertises as **`FlySpark F4 v2`**, HM-10 / CC2541 style serial (service `FFE0` / characteristic `FFE1`).
- 🔁 Transparent bridge: **MSP** (Betaflight, INAV) and **MAVLink** (ArduPilot) pass straight through.
- 🔋 Drives the **4 battery LEDs** from MSP battery state or MAVLink `SYS_STATUS` — works with every firmware.
- 💡 LED codes: link LED blinks while a phone is connected · all 4 LEDs blink = FC not running flight firmware.
- 🖼️ BLE advertisement carries the FlySpark model ID so the FlySpark app shows the right board picture.

## ⬇️ File

[**FlySpark_BLE_V12.bin**](https://github.com/flyspark015/FlySpark/raw/main/FC/FlySpark-F4-V1/firmware/bluetooth/FlySpark_BLE_V12.bin) — merged image, flash at **0x0**.

## 🛠️ Flash (needs the FlySpark ESP32 programming fixture / UART adapter on the ESP pads)

```bash
pip install esptool
esptool --chip esp32c3 -p <PORT> -b 115200 write-flash 0x0 FlySpark_BLE_V12.bin
```

> ⚠️ Use **115200 baud** — higher speeds are unreliable on the fixture. On Windows `<PORT>` is e.g. `COM8`,
> on macOS `/dev/cu.usbserial-0001`.
