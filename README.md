# Raspberry Pi CM0IQ
Tiniest Raspberry Pi board, measuring just 42x36mm! CM0IQ board is based on Raspberry Pi/EDATEC CM0 Compute module

# Features
- Raspberry Pi CM0 Lite
  - 1GHz quad-core 64-bit Arm Cortex-A53 processor
  - 512MB SDRAM
  - H.264/MPEG-4 video decoding, 1080p@30fps
  - H.264 encoding, 1080p@30fps
  - WiFi with extermal antenna connector
- USB type-C for power and gadget mode
- USB-A
- HDMI type D (micro HDMI)
- DSI 4-lane
- CSI 4-lane
- 40-pin GPIO connector, 1.27mm pitch
- SD-card holder
- 5V solder pads
- M2 x4 standoffs for mounting the board

![CM0IQ](CM0IQ-1.jpg)
![CM0IQ](CM0IQ-3.jpg)

# CM0IQ vs RPi Zero 2W

| Feature        | CM0IQ                     | RPi Zero 2W                  |
| -------------- | ------------------------- | ---------------------------- |
| Dimentions     | 42x36mm, 15.1cm<sup>2</sup> | 65x30mm, 19.5cm<sup>2</sup> |
| Camera         | CSI 4 lanes               | CSI 2 lanes                  |
| Display        | DSI 4 lanes               | None                         |
| HDMI           | Micro-HDMI                | Mini-HDMI                    |
| USB host       | USB-A connector           | Micro-USB (adapter required) |
| GPIO connector | 40-pin 1.27mm pitch       | 40-pin 2.54mm pitch          |
| Antenna        | IPEX-1  antenna connector | Integrated PCB antenna       |

# Mechanical
CM0IQ outline dimentions are 42x36mm. Four mounting points are M2x0.4 threaded standoffs with 2mm max depth. Standoff height is 1mm

IMPORTANT: screwing deeply than 2mm can permanently damage the board

![Dimentions](Mounting_points.png)

# GPIO Connector
CM0IQ board has 40-pin 1.27mm pitch GPIO connector, using standard Raspberry Pi GPIO pinout

Pin 1 location:

![Pin1_location](PCB_top.png)

# DSI Connector
Connector has standard Raspberry Pi 22-pin DSI connector pinout

DSI displays are not automatically detected and configuration to config.txt shall be added. 

Example for 5" Raspberry Pi Touch Display 2:
```
dtoverlay=vc4-kms-dsi-ili9881-5inch
```

Note: Raspberry Pi Touch Display 2 5V power has to be provided separately. 5V is available on GPIO connector, as well as on solder pads at the corner of the board

# CSI Connector
Connector has standard Raspberry Pi 22-pin CSI connector pinout. Camera modules are not automatically detected and configuration shall be added, for example (Raspberry Pi Camera Module 3):
```
dtoverlay=imx708
```

# DIP-switch

| Switch         | Off                                  | On                                    |
| -------------- | ------------------------------------ | ------------------------------------- |
| 1              | Normal operation                     | nRPI_BOOT low                         |
| 2              | USB data switched to USB-C connector | USB data switched to USB-A connector  |
