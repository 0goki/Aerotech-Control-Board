# High Voltage Digital Level Shifter

![IMG_5034](https://github.com/user-attachments/assets/6bfabe3d-b57f-4cef-a40a-acb8066a557a)

An ESP32-based microcontroller with an opto-isolated level shifter designed to take up to 3 separate 5V TTL signals and output up to 12 channels of digital signals at 5-24V without signal inversion. The 12-channel output is also configured with flyback diodes and an isolated ground, serving as a solenoid driver supporting 12 solenoids with a total power draw of 24V at 5A.

Designed for Aerotech gantry systems running Automation1 and wired for Position Synchronized Output (PSO).

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

## PCB Specs

<img width="1200" height="836" alt="sm_black_top" src="https://github.com/user-attachments/assets/35cbbdf6-8c85-434f-909e-3500baba582c" />

- 2 layers
- 1.6mm thickness
- ENIG finish

## Bill of Materials

[Interactive BOM](https://0goki.github.io/MB01202026.html)

[Digikey BOM](http://www.digikey.com/short/v1b47t42)

## Revisions

| Mainboard | EDA | Production Notes |
| ------------- | ------------- | ------------- |
| MB01202026  | KICAD Nightly 9.99 | First physical production run with JLCPCB. |

| Breakout | EDA | Production Notes |
| ------------- | ------------- | ------------- |
| BO01162026 | KICAD Nightly 9.99 | First physical production run with JLCPCB. |

## Breakout/Daughterboards

<img width="1200" height="237" alt="sm_white_top" src="https://github.com/user-attachments/assets/46c673bb-b144-46be-9756-3017a54b88fc" />

The PCB includes built-in pogo pin connectors to support various breakout/daughterboard options.

[Github page to H-Bridge breakout board.](https://github.com/0goki/-HVDLS-HBridge)
