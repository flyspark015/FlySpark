<div align="center">

# 💾 FlySpark F4 V1 — Firmware

[⬅️ Back to FlySpark F4 V1](../README.md) · [🏠 FlySpark home](../../../README.md)

</div>

> ✅ All builds are made from the **official release tags** of each project, with FlySpark defaults for the
> F4 V1 + BLS 60A stack (DShot300, no current sensor, Bluetooth port ready). Source changes are published as `.patch` files.

## ⬇️ Downloads

| Firmware | Version | Download | Use it for |
|---|---|---|---|
| 🟡 **Betaflight** | 2026.6.2 | [**betaflight_2026.6.2_FLYSPARKF4.hex**](https://github.com/flyspark015/FlySpark/raw/main/FC/FlySpark-F4-V1/firmware/betaflight/betaflight_2026.6.2_FLYSPARKF4.hex) · [guide](betaflight) | Freestyle, racing, cinematic FPV |
| 🔵 **INAV** | 9.1.0 | [**inav_9.1.0_FlySparkF4v1.hex**](https://github.com/flyspark015/FlySpark/raw/main/FC/FlySpark-F4-V1/firmware/inav/inav_9.1.0_FlySparkF4v1.hex) · [guide](inav) | GPS, position hold, RTH, waypoints, wings |
| 🟢 **ArduCopter** | 4.7.1 | [**.apj** (Mission Planner)](https://github.com/flyspark015/FlySpark/raw/main/FC/FlySpark-F4-V1/firmware/ardupilot/copter/arducopter_4.7.1_FlysparkF4.apj) · [**_with_bl.hex** (first install)](https://github.com/flyspark015/FlySpark/raw/main/FC/FlySpark-F4-V1/firmware/ardupilot/copter/arducopter_4.7.1_FlysparkF4_with_bl.hex) · [guide](ardupilot) | Multirotor missions, survey, autonomy |
| 🟢 **ArduPlane** | 4.7.1 | [**.apj** (Mission Planner)](https://github.com/flyspark015/FlySpark/raw/main/FC/FlySpark-F4-V1/firmware/ardupilot/plane/arduplane_4.7.1_FlysparkF4.apj) · [**_with_bl.hex** (first install)](https://github.com/flyspark015/FlySpark/raw/main/FC/FlySpark-F4-V1/firmware/ardupilot/plane/arduplane_4.7.1_FlysparkF4_with_bl.hex) · [guide](ardupilot) | Fixed wing, VTOL (QuadPlane) |
| 📶 **Bluetooth bridge** | V12 | [**FlySpark_BLE_V12.bin**](https://github.com/flyspark015/FlySpark/raw/main/FC/FlySpark-F4-V1/firmware/bluetooth/FlySpark_BLE_V12.bin) · [guide](bluetooth) | On-board ESP32-C3 (factory installed) |

🔐 Checksums: [SHA256SUMS.txt](SHA256SUMS.txt)

## 🔁 Switching firmware

```text
Betaflight  ⇄  INAV        flash the .hex in the other configurator (Full chip erase ON)
Betaflight / INAV  →  ArduPilot   flash  *_with_bl.hex  once (DFU), then use .apj updates in Mission Planner
ArduPilot  →  Betaflight / INAV   hold BOOT while plugging USB-C (DFU), flash the .hex
```

> 💡 **DFU mode:** hold the **BOOT** button while plugging in USB-C. Windows needs the *STM32 BOOTLOADER* WinUSB
> driver once (Betaflight App → *Driver install* or **ImpulseRC Driver Fixer** / **Zadig**).

## 🧾 Defaults in FlySpark builds

| Setting | 🟡 Betaflight | 🔵 INAV | 🟢 ArduPilot |
|---|---|---|---|
| Motor protocol | DShot300 (apply [CLI defaults](betaflight/flyspark_cli_defaults.txt)) | **DShot300** | **MOT_PWM_TYPE 5** (DShot300) |
| Bidirectional DShot | OFF | — | OFF |
| Current meter | NONE | **OFF** | **BATT_MONITOR 3** (voltage only) |
| Bluetooth (UART4) | MSP 115200 | MSP 115200 | **MAVLink2 115200** |
| Receiver | UART2 serial RX | UART2 SBUS | SERIAL2 RC input |
