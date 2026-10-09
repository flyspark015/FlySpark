<div align="center">

# 🟡 Betaflight 2026.6.2 — FlySpark F4 V1 / V2

[![Betaflight](https://img.shields.io/badge/Betaflight-2026.6.2-FFBB00?style=for-the-badge)](https://github.com/betaflight/betaflight/releases/tag/2026.6.2)
[![Target](https://img.shields.io/badge/Target-FLYSPARKF4-222?style=for-the-badge)](config.h)
[![Status](https://img.shields.io/badge/Hardware-verified-2EA44F?style=for-the-badge)](#-tested)

[⬅️ All firmware](../README.md)

</div>

## ⬇️ Files

| File | What it is |
|---|---|
| [**betaflight_2026.6.2_FLYSPARKF4.hex**](https://github.com/flyspark015/FlySpark/raw/main/FC/FlySpark-F4-V1/firmware/betaflight/betaflight_2026.6.2_FLYSPARKF4.hex) | Full-feature build of the official `FLYSPARKF4` target |
| [config.h](config.h) | Official FLYSPARKF4 board config (pins, timers, defaults) |
| [flyspark_cli_defaults.txt](flyspark_cli_defaults.txt) | Paste into CLI after flashing (FlySpark stack defaults) |

**Included features:** CRSF · ELRS · GHST · SBUS · IBUS · FPORT · Spektrum · SRXL2 · SmartPort / LTM telemetry · DShot ·
GPS + GPS Rescue · Mag · LED strip · OSD (analog + HD) · VTX · PINIO · Rangefinder · Optical flow · Alt Hold · Pos Hold ·
Camera control · Acro trainer · Battery continue.

## 🛠️ Flash

1. Open the **[Betaflight App](https://app.betaflight.com)** (or Betaflight Configurator) → **Firmware Flasher**.
2. Either choose board **`FLYSPARKF4`** online, or click **Load Firmware [Local]** and pick the `.hex` above.
3. Enable **Full chip erase** → **Flash Firmware**. The board enters DFU by itself.
   *Stuck / empty board?* Hold **BOOT** while plugging USB-C, then flash.
4. Connect → **CLI** → paste [flyspark_cli_defaults.txt](flyspark_cli_defaults.txt) → Enter.

## ⚙️ FlySpark defaults

```text
set motor_pwm_protocol = DSHOT300
set dshot_bidir = OFF
set current_meter = NONE
serial UART4 1 115200 57600 0 115200
save
```

- 📶 UART4 = on-board Bluetooth (MSP 115200) — keep it enabled for the FlySpark app.
- 📡 Receiver on UART2 (SBUS pad = inverted SBUS, RX2/TX2 = CRSF/ELRS).

## ✅ Tested

| Check | Result |
|---|---|
| Flash + read-back verify (DFU) | ✅ |
| MSP identify `BTFL 2026.6.2 FLYSPARKF4` | ✅ |
| Gyro + acc (ICM-42688-P) + baro (DPS310) | ✅ |
| Bluetooth MSP from phone/PC | ✅ |
| FlySpark defaults applied + read back (DShot300, bidir OFF, current NONE, UART4 MSP) | ✅ |
