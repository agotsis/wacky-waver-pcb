# Wacky Waver PCB

Control board for a desktop-sized inflatable tube guy (wacky waver). Drives the blower motor via WiFi using a Seeed XIAO ESP32-C5.

## Overview

| Component | |
|---|---|
| MCU | Seeed XIAO ESP32-C5 (SMD) |
| Motor driver | MOSFET (SUD50P10-43L or FQD13N10LTM) |
| Connector | 2-pin blower motor |
| Power | USB-C via XIAO onboard regulator |

## Project Structure

```
wacky-waver.kicad_sch  # schematic
wacky-waver.kicad_pcb  # PCB layout
wacky-waver.kicad_pro  # project settings
```

## Choosing a FET (Q1)

Both options are N-channel MOSFETs in TO-252-3 (DPak). The key differences are VGS threshold and ID saturation:

- **FQD13N10LTM:** lower VGS threshold, compatible with 3.3 V logic-level gate drive. Lets you do variable speed control. (recommended)
- **SUD50P10-43L:** higher ID saturation, more current headroom. Use this if you only need on/off control.

## Component References

| Ref | Part | Datasheet |
|---|---|---|
| U1 | Seeed XIAO ESP32-C5 (SMD) | [Seeed Wiki](https://wiki.seeedstudio.com/xiao_esp32c5_getting_started/) |
| Q1 | FQD13N10LTM (N-ch MOSFET) | [onsemi](https://www.onsemi.com/download/data-sheet/pdf/fqd13n10-d.pdf) |
| Q1 | SUD50P10-43L (N-ch MOSFET, alt) | [Vishay](https://www.vishay.com/docs/62504/sud50p10-43l-ge3.pdf) |

## Building

Open `wacky-waver.kicad_pro` in KiCad 10+.

Gerbers for fabrication are attached to each [GitHub release](../../releases).
