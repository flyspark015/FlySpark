<div align="center">

# 🟢 ArduPilot 4.7.1 — FlySpark F4 V1 (Mission Planner)

[![ArduCopter](https://img.shields.io/badge/ArduCopter-4.7.1-1E9E40?style=for-the-badge)](https://github.com/ArduPilot/ardupilot/tree/Copter-4.7.1)
[![ArduPlane](https://img.shields.io/badge/ArduPlane-4.7.1-1E9E40?style=for-the-badge)](https://github.com/ArduPilot/ardupilot/tree/Plane-4.7.1)
[![Board](https://img.shields.io/badge/Board-FlysparkF4_(ID_1361)-222?style=for-the-badge)](https://github.com/ArduPilot/ardupilot/tree/Copter-4.7.1/libraries/AP_HAL_ChibiOS/hwdef/FlysparkF4)

[⬅️ All firmware](../README.md)

</div>

## ⬇️ Files

| Vehicle | For Mission Planner / QGC updates | First install from Betaflight / INAV (DFU) |
|---|---|---|
| 🚁 **ArduCopter 4.7.1** | [arducopter_4.7.1_FlysparkF4.apj](https://github.com/flyspark015/FlySpark/raw/main/FC/FlySpark-F4-V1/firmware/ardupilot/copter/arducopter_4.7.1_FlysparkF4.apj) | [arducopter_4.7.1_FlysparkF4_with_bl.hex](https://github.com/flyspark015/FlySpark/raw/main/FC/FlySpark-F4-V1/firmware/ardupilot/copter/arducopter_4.7.1_FlysparkF4_with_bl.hex) |
| ✈️ **ArduPlane 4.7.1** | [arduplane_4.7.1_FlysparkF4.apj](https://github.com/flyspark015/FlySpark/raw/main/FC/FlySpark-F4-V1/firmware/ardupilot/plane/arduplane_4.7.1_FlysparkF4.apj) | [arduplane_4.7.1_FlysparkF4_with_bl.hex](https://github.com/flyspark015/FlySpark/raw/main/FC/FlySpark-F4-V1/firmware/ardupilot/plane/arduplane_4.7.1_FlysparkF4_with_bl.hex) |

Also here: [defaults.parm](defaults.parm) (built into the firmware) · [flyspark_ardupilot_4.7.1.patch](flyspark_ardupilot_4.7.1.patch) (source change, GPL)

## 🛠️ First install (board has Betaflight / INAV)

1. Hold **BOOT** while plugging USB-C → the board is in **DFU** (Windows: *STM32 BOOTLOADER*, needs WinUSB driver once —
   use **ImpulseRC Driver Fixer** or **Zadig**).
2. Flash the **`_with_bl.hex`** with **Betaflight App / Configurator** (*Load Firmware [Local]*, Full chip erase) or
   **STM32CubeProgrammer** (USB, address 0x08000000).
3. Unplug / replug. Open **Mission Planner** → connect on the new COM port at 115200.

## 🔄 Updates (board already runs ArduPilot)

**Mission Planner** → *Setup* → *Install Firmware* → **Load custom firmware** → pick the `.apj`.
(Mission Planner's own list also has board **FlysparkF4** — that is the plain upstream build; load the FlySpark defaults below.)

## ⚙️ FlySpark defaults (built in)

```text
BATT_MONITOR      3     # voltage only - the BLS 60A ESC has no current sensor
SERIAL4_PROTOCOL  2     # UART4 = on-board Bluetooth bridge, MAVLink2
SERIAL4_BAUD      115   # 115200
MOT_PWM_TYPE      5     # DShot300 for BLHeli_S J_H_40 (Copter)
Q_M_PWM_TYPE      5     # DShot300 for QuadPlane lift motors (Plane)
SERVO9_FUNCTION   120   # LED strip on the LED pad
OSD_TYPE2         5     # MSP DisplayPort (DJI / HD) on UART1
```

| SERIAL | Port | Default |
|---|---|---|
| 0 | USB | MAVLink2 |
| 1 | UART1 / DJI plug | MSP DisplayPort |
| 2 | UART2 / SBUS pad | RC input |
| 3 | UART3 | free |
| 4 | UART4 (internal) | 📶 Bluetooth MAVLink2 115200 |
| 5 | UART5 RX (TEL pad) | ESC telemetry |
| 6 | UART6 | GPS |

> 🧭 **Always check orientation** before the first flight: in Mission Planner tilt the board nose-down / right-down and
> confirm the HUD follows. Board defaults: `AHRS_ORIENTATION 0`. No compass on board — add one on I²C for GPS modes.

## ✅ Status

| Check | Result |
|---|---|
| Built from tags `Copter-4.7.1` / `Plane-4.7.1` (board `FlysparkF4`, APJ ID 1361) | ✅ |
| FlySpark defaults embedded in ROMFS | ✅ |
| On-board bench test (flash, sensors, orientation, Bluetooth) | 🧪 in progress |
