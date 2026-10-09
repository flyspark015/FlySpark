<div align="center">

# ⚙️ FlySpark BLS 60A 4-in-1 ESC

[![BLHeli_S](https://img.shields.io/badge/BLHeli__S-J__H__40_16.7-E53935?style=for-the-badge)](firmware)
[![Rating](https://img.shields.io/badge/60A_cont-80A_burst-222?style=for-the-badge)](#-specs)
[![Input](https://img.shields.io/badge/LiPo-3--6S-F5C400?style=for-the-badge)](#-specs)

[🛒 Buy ESC](https://flyspark.in/products/flyspark-bls-60a-4-in-1-esc) · [🛒 Buy F4 stack](https://flyspark.in/products/flyspark-f4-v1-bls-60a-stack-flight-controller-4-in-1-esc) · [🧠 FlySpark F4 V1](../../FC/FlySpark-F4-V1) · [🏠 Home](../../README.md)

</div>

## 📋 Specs

| | |
|---|---|
| ⚡ Continuous / burst | 60 A / 80 A (10 s) per motor |
| 🔋 Input | 3–6S LiPo (TVS protected) |
| 🧠 MCU | SiLabs EFM8BB21 |
| 💾 Firmware | BLHeli_S **J_H_40** rev 16.7 |
| 📡 Protocols | DShot150 / 300 / 600, Oneshot125, PWM |
| 🔌 Harness | 8-pin JST to FC (GND, VBAT, M1–M4, current, TEL) |
| 📏 Current sensor | ❌ none (set current meter **OFF** on the FC) |
| 📐 Mounting | 30.5 × 30.5 mm |

## ⚙️ Recommended FC settings

| Firmware | Setting |
|---|---|
| 🟡 Betaflight | `motor_pwm_protocol = DSHOT300` · `dshot_bidir = OFF` · `current_meter = NONE` |
| 🔵 INAV | `motor_pwm_protocol = DSHOT300` · `feature -CURRENT_METER` |
| 🟢 ArduPilot | `MOT_PWM_TYPE 5` · `BATT_MONITOR 3` |

> BLHeli_S J_H_40 does **not** support bidirectional DShot / RPM filter — keep it OFF.

## 🧾 Factory ESC settings (BLHeliSuite / ESC-Configurator)

| Setting | Value | Setting | Value |
|---|---|---|---|
| Startup power | 0.50 | Motor direction | Normal |
| Programming by TX | ON | Motor timing | Medium |
| PPM min / max / center | 1148 / 1832 / 1488 | Demag compensation | Low |
| Beep strength | 40 | Beacon strength | 80 |
| Beacon delay | 10 min | Temperature protection | 140 °C |
| Low RPM power protect | ON | Brake on stop | OFF |
| LED control | OFF | Names | `FlySpark ESC M1` … `M4` |

> 🔔 Beeping every few seconds after ~10 minutes on the bench = the ESC **beacon** (no signal). Normal — arm or unplug.

## 💾 Firmware

| File | Use |
|---|---|
| [**J_H_40_REV16_7.HEX**](https://github.com/flyspark015/FlySpark/raw/main/ESC/FlySpark-BLS-60A/firmware/J_H_40_REV16_7.HEX) | Official BLHeli_S 16.7 for layout **J-H-40** |

**Reflash / restore:** connect the FC by USB (battery plugged in, props off) → open
[ESC-Configurator](https://esc-configurator.com) or BLHeliSuite 16 → *Read Setup* → *Flash Local* → `J_H_40_REV16_7.HEX`
→ write the settings above.
