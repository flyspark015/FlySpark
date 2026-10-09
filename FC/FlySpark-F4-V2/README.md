<div align="center">

# 🟨 FlySpark F4 V2 Flight Controller

<img src="../FlySpark-F4-V1/images/flyspark_f4_fc.png" alt="FlySpark F4 V2 flight controller" width="420">

**The current FlySpark F4 — upgraded build quality, same proven F405 layout.**
Built-in Bluetooth, OSD, SD blackbox, 8 motor outputs. Runs **Betaflight**, **INAV** and **ArduPilot**.

[![Latest](https://img.shields.io/badge/✨_Version-V2_(current)-F5C400?style=for-the-badge)](#-whats-new-in-v2)
[![Betaflight](https://img.shields.io/badge/Betaflight-2026.6.2-FFBB00?style=for-the-badge)](../FlySpark-F4-V1/firmware/betaflight)
[![INAV](https://img.shields.io/badge/INAV-9.1.0-0090D0?style=for-the-badge)](../FlySpark-F4-V1/firmware/inav)
[![ArduPilot](https://img.shields.io/badge/ArduPilot-4.7.1-1E9E40?style=for-the-badge)](../FlySpark-F4-V1/firmware/ardupilot)

[💾 Firmware downloads](../FlySpark-F4-V1/firmware) · [📍 Full pinout](../FlySpark-F4-V1#-pinout--port-map) · [💬 Order V2 on WhatsApp](https://wa.me/916375729997) · [⬅️ All FCs](../README.md)

</div>

---

## ✨ What's new in V2

| | V1 | **V2** |
|---|:---:|:---:|
| 🛠️ Hardware build quality | standard | ✅ **upgraded** |
| 📍 Pinout, pads, connectors, mounting | ✅ | ✅ identical |
| 🧠 STM32F405 · ICM-42688-P · DPS310 · MAX7456 · microSD | ✅ | ✅ |
| 📶 Bluetooth name | `FlySpark F4 v1` (old bridge) | **`FlySpark F4 v2`** |
| 📶 Bluetooth bridge firmware | earlier vendor bridge | ✅ **FlySpark V12** (MSP + MAVLink, live battery gauge) |
| 💾 Factory firmware | earlier Betaflight | ✅ **Betaflight 2026.6.2**, flashed + tested on our production station |

> 🔁 **Same firmware for V1 and V2.** Every file on the [firmware page](../FlySpark-F4-V1/firmware) works on both boards.
> A V1 can be brought up to V2 software by flashing the same Betaflight / INAV / ArduPilot files and the
> [Bluetooth V12](../FlySpark-F4-V1/firmware/bluetooth) bridge.

---

## 📋 Specs

| | |
|---|---|
| 🧠 **MCU** | STM32F405RGT6 · 168 MHz · 1 MB flash |
| 🎯 **Gyro / Acc** | ICM-42688-P (SPI1) |
| 🌡️ **Barometer** | DPS310 (I²C1, 0x76) |
| 📺 **OSD** | MAX7456 analog + DJI / HD DisplayPort (UART1 / DJI plug) |
| 💾 **Blackbox** | microSD |
| 📶 **Bluetooth** | ESP32-C3 on UART4 · `FlySpark F4 v2` · FlySpark app, Betaflight App, SpeedyBee app, ArduPilot MAVLink |
| 🔋 **Battery gauge** | 4 LEDs · works with all three firmwares |
| 🔌 **Outputs** | M1–M8 · LED strip · buzzer · camera control |
| 🔁 **UARTs** | 6 (UART4 = Bluetooth) · SBUS input with hardware inverter |
| ⚡ **Power** | 3–6S · 5 V 3 A · 9 V 3 A · 3.3 V · 4.5 V |
| 📐 **Mounting** | 30.5 × 30.5 mm |

---

## 🗺️ Wiring

<table>
<tr>
<td width="50%"><img src="../FlySpark-F4-V1/images/wiring_fc_peripherals.png" alt="FC connection diagram"></td>
<td width="50%"><img src="../FlySpark-F4-V1/images/wiring_fc_to_esc.png" alt="FC to ESC connection"></td>
</tr>
<tr>
<td align="center">📡 Receivers · GPS · VTX · DJI · LED · buzzer</td>
<td align="center">🔌 FC ↔ ESC 8-pin harness</td>
</tr>
</table>

📍 UART map per firmware, motor timers and all pins: **[full pinout](../FlySpark-F4-V1#-pinout--port-map)** (identical on V1 and V2).

---

## 💾 Firmware (V1 + V2)

| | Version | Download |
|---|---|---|
| 🟡 **Betaflight** | 2026.6.2 | [betaflight_2026.6.2_FLYSPARKF4.hex](https://github.com/flyspark015/FlySpark/raw/main/FC/FlySpark-F4-V1/firmware/betaflight/betaflight_2026.6.2_FLYSPARKF4.hex) · [guide](../FlySpark-F4-V1/firmware/betaflight) |
| 🔵 **INAV** | 9.1.0 | [inav_9.1.0_FlySparkF4v1.hex](https://github.com/flyspark015/FlySpark/raw/main/FC/FlySpark-F4-V1/firmware/inav/inav_9.1.0_FlySparkF4v1.hex) · [guide](../FlySpark-F4-V1/firmware/inav) |
| 🟢 **ArduCopter** | 4.7.1 | [.apj](https://github.com/flyspark015/FlySpark/raw/main/FC/FlySpark-F4-V1/firmware/ardupilot/copter/arducopter_4.7.1_FlysparkF4.apj) · [_with_bl.hex](https://github.com/flyspark015/FlySpark/raw/main/FC/FlySpark-F4-V1/firmware/ardupilot/copter/arducopter_4.7.1_FlysparkF4_with_bl.hex) · [guide](../FlySpark-F4-V1/firmware/ardupilot) |
| 🟢 **ArduPlane** | 4.7.1 | [.apj](https://github.com/flyspark015/FlySpark/raw/main/FC/FlySpark-F4-V1/firmware/ardupilot/plane/arduplane_4.7.1_FlysparkF4.apj) · [_with_bl.hex](https://github.com/flyspark015/FlySpark/raw/main/FC/FlySpark-F4-V1/firmware/ardupilot/plane/arduplane_4.7.1_FlysparkF4_with_bl.hex) · [guide](../FlySpark-F4-V1/firmware/ardupilot) |
| 📶 **Bluetooth bridge** | V12 | [FlySpark_BLE_V12.bin](https://github.com/flyspark015/FlySpark/raw/main/FC/FlySpark-F4-V1/firmware/bluetooth/FlySpark_BLE_V12.bin) · [guide](../FlySpark-F4-V1/firmware/bluetooth) |

> ℹ️ In Betaflight the target is **`FLYSPARKF4`**, in INAV **`FlySparkF4v1`**, in ArduPilot / Mission Planner **`FlysparkF4`** —
> the names come from the upstream projects and are correct for V2 too.

---

## 🔌 Stack: FlySpark F4 V2 + BLS 60A

Pairs with the **[FlySpark BLS 60A 4-in-1 ESC](../../ESC/FlySpark-BLS-60A)** (BLHeli_S J_H_40 16.7, 3–6S) on the 8-pin harness —
DShot300, bidirectional DShot OFF, current meter OFF. Stack guide: [F4 stack section](../FlySpark-F4-V1#-stack-flyspark-f4-v1--bls-60a).

---

## 🛟 Help

[🐞 Open a support issue](https://github.com/flyspark015/FlySpark/issues/new/choose) · [💬 WhatsApp +91 63757 29997](https://wa.me/916375729997) · [✉️ info@flyspark.in](mailto:info@flyspark.in) · [🌐 flyspark.in](https://flyspark.in)
