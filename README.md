# Aerotech Control Board

![IMG_5034](https://github.com/user-attachments/assets/6bfabe3d-b57f-4cef-a40a-acb8066a557a)

A Teensy 4.1-based I/O expansion microcontroller.

Designed for Aerotech gantry systems running Automation1 and wired for Position Synchronized Output (PSO) and Digital Outputs (DOUT).

## Important Pinouts

| Function | Pin |
| - | - |
| SCK | GPIO 40 |
| MISO | GPIO 39 |
| MOSI | GPIO 41 |
| CS | GPIO 42 |
| CARD_DETECT | GPIO 3 |
| SDA | GPIO 12 |
| SCL | GPIO 13 |
| PSO00 | GPIO 47 |
| PSO01 | GPIO 48 |
| PSO02 | GPIO 45 |

## PCB Specs

- 2-layers
- 1.6mm thickness
- ENIG

## Bill of Materials

[Interactive BOM](https://0goki.github.io/MB01202026.html)

[Digikey BOM](http://www.digikey.com/short/v1b47t42)


## Feature Testing

| Feature | Description | Testing Status | Notes |
| ------------- | ------------- | ------------- | ------------- |
| ESP32-S3 | Microcontroller | Working | Additional GPIO are needed. Planned switch to STM32. |
| USB-C | 5Vin and D+/- | Working | |
| 5V Regulator | For 5V | Working | |
| DC 5-24Vin | For 5-24V input | Working/Issues | Trace width inadequate. Jumper for 5V USB to DC net not properly connected. |
| High Current Mosfets | for 5-24V output | Not Working | Redesign required. Pull up resistor over-wattage. Short to GND. Flyback bridged. |
| Optical Isolator | 3.3V logic isolation | Working | |
| Logic Invertor | Inverts DIO | To Be Removed | Logic does not need negation. |
| SD Card | Read/write data | Working | Read/Write using FAT32. Tested with up to 512GB Sabrent V60. |
| Input 5-to-3.3V Level Shifter | Steps down logic level | Working | Reads 5V TTL. |

## Versions

### Mainboard

| Version | EDA | Notes |
| ------------- | ------------- | ------------- |
| 05222026 (Release 1.2) | KICAD 10.0 | Complete hardware design. Removed ESP32-S3 for Teensy 4.1. |
| MB01202026  | KICAD Nightly 9.99 | First physical production run with JLCPCB. |

| Version | Board |
| ------------- | ------------- |
| 05222026 (Release 1.2) | <img width="7684" height="3549" alt="f1f942433f7626ced174f3de3951ec44" src="https://github.com/user-attachments/assets/a9068e6b-3f3d-4a2e-add5-8225bf59c7d9" /> |
| MB01202026  | <img width="1200" height="836" alt="sm_black_top" src="https://github.com/user-attachments/assets/35cbbdf6-8c85-434f-909e-3500baba582c" /> |

### Breakout [Deprecated]

| Version | EDA | Notes |
| ------------- | ------------- | ------------- |
| Deprecated | | Removed need for breakouts. |
| BO01162026 | KICAD Nightly 9.99 | First physical production run with JLCPCB. |

| Version | Board |
| ------------- | ------------- |
| Deprecated | |
| BO01162026 | <img width="1200" height="237" alt="sm_white_top" src="https://github.com/user-attachments/assets/46c673bb-b144-46be-9756-3017a54b88fc" /> |

The PCB includes built-in pogo pin connectors to support various breakout/daughterboard options.

[Github page to H-Bridge breakout board.](https://github.com/0goki/-HVDLS-HBridge)
