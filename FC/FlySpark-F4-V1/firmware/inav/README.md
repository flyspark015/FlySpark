<div align="center">

# 🔵 INAV 9.1.0 — FlySpark F4 V1

[![INAV](https://img.shields.io/badge/INAV-9.1.0-0090D0?style=for-the-badge)](https://github.com/iNavFlight/inav/releases/tag/9.1.0)
[![Target](https://img.shields.io/badge/Target-FlySparkF4v1-222?style=for-the-badge)](https://github.com/iNavFlight/inav/tree/9.1.0/src/main/target/FLYSPARKF4V4)

[⬅️ All firmware](../README.md)

</div>

## ⬇️ Files

| File | What it is |
|---|---|
| [**inav_9.1.0_FlySparkF4v1.hex**](https://github.com/flyspark015/FlySpark/raw/main/FC/FlySpark-F4-V1/firmware/inav/inav_9.1.0_FlySparkF4v1.hex) | Official INAV 9.1.0 `FlySparkF4v1` target + FlySpark stack defaults |
| [flyspark_inav_9.1.0.patch](flyspark_inav_9.1.0.patch) | The exact source change (GPL) |

## 🛠️ Flash

1. Install **[INAV Configurator 9.x](https://github.com/iNavFlight/inav-configurator/releases)**.
2. **Firmware Flasher** → **Load Firmware [Local]** → pick `inav_9.1.0_FlySparkF4v1.hex`.
3. Enable **Full chip erase** → **Flash Firmware**. (Empty board / coming from ArduPilot: hold **BOOT** while plugging USB-C.)
4. Connect and run the **setup wizard** (mixer, receiver, outputs), calibrate the accelerometer.

> ℹ️ INAV Configurator also offers the target **FlySparkF4v1** online — that is the plain upstream build. If you use it,
> paste the CLI lines below once.

## ⚙️ FlySpark defaults (already in the .hex)

```text
set motor_pwm_protocol = DSHOT300
feature -CURRENT_METER
save
```

| Port | Default |
|---|---|
| UART2 | Serial RX · SBUS (SBUS pad has the on-board inverter; use RX2/TX2 for CRSF/ELRS) |
| UART4 | 📶 Bluetooth · MSP 115200 (FlySpark app) |
| UART5 | ESC telemetry (TEL pad) |
| UART6 | free — recommended for **GPS** |
| I²C1 | compass · rangefinder · airspeed |

## ✅ Status

| Check | Result |
|---|---|
| Built from tag `9.1.0` with arm-gnu-toolchain 13.2 | ✅ |
| Pins / timers / UARTs checked against the FlySpark F4 V1 schematic | ✅ |
| On-board bench test (flash, sensors, orientation, Bluetooth) | 🧪 in progress |
