# Starforge-Dev-Board
A simple 4 layer RP2040 Dev Board powered by USB-C, with data and power delivery. Uses 24 GPIO and 4 ADC pins, alongside 1 3.3V and one 5V output. There is also 7 ground pins with 2 debug pins. It also has a red signal LED for any use case, utilizing the single unused standard GPIO pin.

My goal with this project was to learn how to route properly and effectively on a PCB including how to manage decoupling caps and general power routing because that is what I struggle with. I also wanted a simple board to use for my projects.

This project should:
- help me develop a base to apply to future projects
- be a simple dev board I can use for other projects


## PCB
Here is my PCB! This PCB was designed in KiCAD.

### General PCB design images

Schematic:

<img width="3508" height="2480" alt="image" src="https://github.com/user-attachments/assets/fdee61f6-0786-4a1b-a77f-cbe217770ccb" />

Top View (3d render):

<img width="466" height="1058" alt="image" src="https://github.com/user-attachments/assets/9230ee83-5d37-4a1c-bc2f-9c55015afb2d" />

Bottom View (3d render):

<img width="532" height="1284" alt="image" src="https://github.com/user-attachments/assets/6c1a2f1e-ea2e-421a-a86e-bfcb73d41b78" />

PCB Design:

<img width="376" height="894" alt="image" src="https://github.com/user-attachments/assets/6cbb52b2-e197-4bf4-80cf-c21a44a5dd5b" />

First Layer: 

<img width="410" height="932" alt="image" src="https://github.com/user-attachments/assets/7fcc67b6-26ea-49b5-9a0f-4a38eeb8b33a" />

Second Layer:

<img width="396" height="888" alt="image" src="https://github.com/user-attachments/assets/767aaeb2-cecd-4ef0-8fd6-b112b50ee79b" />

Third Layer: 

<img width="376" height="886" alt="image" src="https://github.com/user-attachments/assets/48883fce-bbac-48db-86ea-011b6dab3735" />

Fourth Layer: 

<img width="408" height="878" alt="image" src="https://github.com/user-attachments/assets/03505ff4-06b9-4457-b91a-62e93001006e" />



### Layer Stackup
The board contains 4 layers. The purpose of all layers listed below.

| Layer | Description |
| :--- | :--- |
| 1 | Main routing layer |
| 2 | First ground layer for reference and signal separation |
| 3 | Second ground layer for reference and signal separation |
| 4 | Overflow routing layer |
### Flashing Instructions
Here are steps to flash a file to the MCU! 
1. Hold down the BOOTSEL button (the only button on the board) while plugging the board into your computer via USBC
2. The board will show up as a USB mass storage device
3. Compile your .uf2 binary file through external methods (C/C++ SDK, MicroPython, CircuitPython, etc)
4. Drag your compiled .uf2 file onto the drive. The board should automatically reboot and run the newly uploaded firmware!

## BOM

All SMD parts utilize 0402 passives to minimize board surface area. JLCPCB / LCSC part numbers are included below for reference.

| Item | Component / Description | Qty | Designators | Footprint | JLCPCB Part # | Unit Price (USD) |
| :--- | :--- | :---: | :--- | :--- | :--- | :--- |
| 1 | RP2040 Microcontroller | 1 | `U1` | `QFN-56_L7.0-W7.0-P0.4` | `C2040` | $0.70 |
| 2 | P25Q16SH-UXH-IR (16Mbit Flash) | 1 | `U3` | `USON8_L3.0-W2.0-P0.5` | `C7466821` | $0.15 |
| 3 | MCP1700T-3302E/TT (3.3V LDO) | 1 | `U2` | `SOT-23` | `C39051` | $0.44 |
| 4 | HC-TYPE-C-16P-01A (USB-C) | 1 | `J1` | `USB_C_Receptacle_16P` | `C2894897` | $0.25 |
| 5 | Crystal_GND24 (12MHz Crystal) | 1 | `Y1` | `SMD_4P-L3.2-W2.5` | `C9002` | $0.09 |
| 6 | TS-1088 Tactile Switch | 1 | `SW1` | `SW-SMD_L3.9-W3.0-P4.45` | `C720477` | $0.05 |
| 7 | Header Male 2.54mm 1x20 | 2 | `J2, J3` | `PinHeader_1x20_P2.54mm` | `C50981` | $0.10 |
| 8 | Header Male 2.54mm 1x3 | 1 | `H1` | `HDR-TH_3P-P2.54mm` | `C2937625` | $0.03 |
| 9 | 100nF Capacitor | 11 | `C2-C9, C11, C12, C17` | `C_0402` | `C1525` | $0.002 |
| 10 | 1uF Capacitor | 2 | `C1, C10` | `C_0402` | `C29266` | $0.003 |
| 11 | 10uF Capacitor | 2 | `C13, C14` | `C_0402` | `C15525` | $0.015 |
| 12 | 33pF Load Capacitor | 2 | `C15, C16` | `C_0402` | `C107005` | $0.002 |
| 13 | 5.1k Resistor | 2 | `R1, R2` | `R_0402` | `C25905` | $0.001 |
| 14 | 27Ω Resistor | 2 | `R5, R6` | `R_0402` | `C2909343` | $0.001 |
| 15 | 1k Resistor | 2 | `R4, R7` | `R_0402` | `C11702` | $0.001 |
| 16 | 10k Resistor | 1 | `R3` | `R_0402` | `C25744` | $0.001 |
| 17 | Tuozhan Red LED (1.91V) | 1 | `D1` | `LED_0603` | `C7496820` | $0.003 |
| 18 | 150Ω Resistor | 1 | `R8` | `R_0402` | `C25082` | $0.001 |
### Prices on JLCPCB:
NOTE: THESE PRICES DO NOT CONTAIN TAXES
PCB (5x): $2.0
PCBA (2x): $48.17
Shipping on Global Standard Direct Line: $3.30

Thanks for viewing this project!
