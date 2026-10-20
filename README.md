# Small devboard 

A custom RP2040-based development board designed from scratch in KiCAD as part of Hack Club Half Life. 

The DevBoard is a compact general-purpose development platform with native USB-C connectivity, external QSPI flash, 3.3V power regulation, GPIO breakout, onboard controls, and a status LED. The board is intended to be used for embedded programming, electronics experimentation, robotics, sensors, displays, and future hardware projects. 

# Features 
- Raspberry Pi RP2040 microcontroller
- Native USB-C connectivity
- External QSPI flash
- 12 MHz crystal oscillator
- 3.3V power regulation
- 2x20 GPIO breakout pins
- BOOTSEL and RESET buttons
- Onboard status LED
- SMD components
- Custom PCB designed in KiCAD

# Hardware 
The board is built around the RP2040 and follows the required circuity for its power, clock, USB, and external flash interfaces. 

# Main components
- RP2040 MCU
- W25Q128 QSPI flash
- 12 MHz crystal
- USB-C connector
- 3.3V LDO regulator
- Decoupling and filtering capacitors
- USB-C CC resistors
- GPIO headers
- RESET and BOOTSEL buttons
- Status LED

# Firmware
The devboard will be programmed using the Raspberry Pi Pico SDK and C/C++. 

The initial firmware will provide: 
- RP2040 boot and initialization
- USB connectivity
- GPIO testing
- Status LED control
- Board diagnostics
- USB serial communication

A diagnostic firmware can be used to verify that the assembled PCB is functioning correctly. 

# PC software
A small optional Python utility may be developed to communicated with the board over USB serial. 

This can be used to 
- Display board information
- Run hardware tests
- Control the onboard LED
- Test GPIO
- Monitor diagnostic output

# Firmware flashing 
The devboard uses the RP2040 microcontroller chip. Compatible UF2 firmware can be flashed over USB without an external programmer, provided the board's USB interface and BOOTSEL circuit are functioning correctly. 

# Requirements
- A USB data cable compatible with the board's USB-C connector
- A computer running either Windows, macOS, or Linux
- A compatible .uf2 firmware file

# Instructions 
1. Obtain the firmware. Download a UF2 firmware file that is compatible with the RP2040 and the intended application. Alternatively, build the firmware from its source code using the appropriate development tools.
2. Enter BOOTSEL mode. Disconnect the devboard from USB. Press and hold the BOOTSEL button, then connect the board to the computer. Release the button after the computer detects the board.
3. Open the bootloader drive. The board should appear as a USB mass-storage device named RPI-RP2. If it does not appear, check the connecting cable, power supply, and BOOTSEL circuit.
4. Copy the firmware. Drag the compatible .uf2 file into the RPI-RP2 drive.
5. Wait for the installation to finish. The drive should disconnect automatically as the RP2040 reboots and begins running the newly installed firmware.
6. Test the board. Verify that the firmware behaves as expected. If the application exposes a USB serial interface, open a serial terminal to inspect its output.

# Troubleshooting 
- The drive does not appear: make sure your USB cable supports data, not just charging. Check that the board receives power and the BOOTSEL circuit is assembled correctly.
- The firmware is rejected or does not run: confirm that the UF2 file targets the RP2040 and is built for the board's memory layout and hardware.
- The board does not behave as expected: try a known-compatible firmware image and inspect the power supply, clock circuit (especially this one), flash connections, and USB data routing.

# Important Notes 
- A UF2 file must be compatible with the RP2040 and the target firmware cofiguration.
- Flashing new firmware replaces the existing application in flash memory.
- BOOTSEL mode is implemented in the RP2040's read-only boot ROM, so compatible hardware can normally re-enter the bootloader even if the installed application fails.
If all else does not work, see the official Raspberry Pi microcontroller chip documentation. 

# Design
The PCB and schematic are designed using KiCAD. 
Project files include: 
- Schematic
- PCB layout
- Component/footprint assignments
- BOM
- Manufacturing files

# Design process
1. select and verify components for pricing and whether it is within budget range
2. create the schematic
3. assign symbols and footprints
4. design the PCB layout
5. route the board
6. run electrical and design rule checks
7. generate gerber files
8. assemble the PCB
9. develop and test firmware
10. test the complete board

# Bill of Materials 
|Item|Qty                          |Supplier|Cost/item                                    |Total Cost|link                                                                                                                                                                                                                                               |
|----|-----------------------------|--------|---------------------------------------------|----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Raspberry Pi RP2040CT|1                            |Cytron  |$1.15                                        |$1.15     |https://my.cytron.io/p-raspberry-pi-rp2040-mcu-ic-single-unit                                                                                                                                                                                      |
|Winbond W25Q128JVSIQ|1                            |LCSC    |$2.52                                        |$2.52     |https://www.lcsc.com/product-detail/C113767.html                                                                                                                                                                                                   |
|12 MHz SMD crystal, 3225 4-pin|5                            |LCSC    |$0.10                                        |$0.50     |https://www.lcsc.com/product-detail/C518158.html                                                                                                                                                                                                   |
|USB Type-C 16-pin receptacle|1                            |Shopee Malaysia|$0.65                                        |$0.65     |https://shopee.com.my/Type-C-3.1-Patch-Socket-6P-16P-24P-Countersunk-Board-1.6-0.8mm-USB-Female-Socket-Data-Interface-i.513412485.42610897264?extraParams=%7B%22display_model_id%22%3A260916036060%2C%22model_selection_logic%22%3A3%7D            |
|3.3 V LDO regulator|1                            |Shopee Malaysia|$0.46                                        |$0.46     |https://shopee.com.my/AMS1117-Voltage-Regulator-IC-SOT-223-1.2V-1.5V-1.8V-2.5V-3.3V-5V-i.1412281456.49416215365?extraParams=%7B%22display_model_id%22%3A396380238012%2C%22model_selection_logic%22%3A3%7D                                          |
|10 µF ceramic capacitor|1                            |Shopee Malaysia|$1.05                                        |$1.05     |https://shopee.com.my/50V-10uF-Multilayer-Capacitor-i.40459773.23082863550?extraParams=%7B%22display_model_id%22%3A138766713726%2C%22model_selection_logic%22%3A3%7D                                                                               |
|100 nF ceramic capacitor|1                            |Shopee Malaysia|$1.25                                        |$1.25     |https://shopee.com.my/0402-0603-0805-1206-100nF-820nF-SMD-Chip-Capacitor-i.1467039591.41834021222?extraParams=%7B%22display_model_id%22%3A218871594639%2C%22model_selection_logic%22%3A3%7D                                                        |
|5.1 kΩ resistor|1                            |Shopee Malaysia|$1.24                                        |$1.24     |https://shopee.com.my/SMD-0402-0603-0805-1206-RESISTOR-1K-9.1K-Ohm-i.1467039591.50009312017?extraParams=%7B%22display_model_id%22%3A307560786040%2C%22model_selection_logic%22%3A3%7D                                                              |
|1 kΩ resistor|1                            |Shopee Malaysia|$1.24                                        |$1.24     |https://shopee.com.my/SMD-0402-0603-0805-1206-RESISTOR-1K-9.1K-Ohm-i.1467039591.50009312017?extraParams=%7B%22display_model_id%22%3A307560786040%2C%22model_selection_logic%22%3A3%7D                                                              |
|0603 LED|1                            |Shopee Malaysia|$0.88                                        |$0.88     |https://shopee.com.my/SMD-0402-0603-0805-1206-RESISTOR-1K-9.1K-Ohm-i.1467039591.50009312017?extraParams=%7B%22display_model_id%22%3A307560786040%2C%22model_selection_logic%22%3A3%7D                                                              |
|Tactile push button|1                            |Shopee Malaysia|$0.31                                        |$0.31     |https://shopee.com.my/Button-Switch-Tactile-Push-6x6x5mm-6*6*5mm-4PIN-i.482535902.11217352127?extraParams=%7B%22display_model_id%22%3A100951846821%2C%22model_selection_logic%22%3A3%7D                                                            |
|Tactile push button|1                            |Shopee Malaysia|$0.31                                        |$0.31     |https://shopee.com.my/Button-Switch-Tactile-Push-6x6x5mm-6*6*5mm-4PIN-i.482535902.11217352127?extraParams=%7B%22display_model_id%22%3A100951846821%2C%22model_selection_logic%22%3A3%7D                                                            |
|2.54 mm male pin headers|1                            |Shopee Malaysia|$0.30                                        |$0.30     |https://shopee.com.my/Male-Header-Pins-Straight-Single-Row-40-Pin-0.1-Inch-(2.54mm)-Male-Pin-Header-Connector-PCB-Board-Pin-Connect-i.161803224.7025057004?extraParams=%7B%22display_model_id%22%3A21946244149%2C%22model_selection_logic%22%3A3%7D|
|Custom PCB|1                            |JLCPCB  |$5.78                                        |$5.78     |https://jlcpcb.com                                                                                                                                                                                                                                 |
|Estimated total shipping|1                            |        |                                             |$7.75     |                                                                                                                                                                                                                                                   
# Project goals
The main goal is to design and build a fully functioning custom development board rather than relying on an existing development board such as the Raspberry Pi Pico. 

The project combines: 
- PCB design
- embedded systems
- electronics
- Firmware development
- USB communication
- hardware testing
- software development

# project images

**Schematic** 

<img width="1225" height="832" alt="image" src="https://github.com/user-attachments/assets/37fe4e7b-f23c-440e-8609-80ea355e5b5b" />

**PCB layout**

<img width="782" height="347" alt="image" src="https://github.com/user-attachments/assets/a1671bb0-82b3-4bf9-bb18-1644ea3dbb10" />

**3d Render**

<img width="767" height="347" alt="image" src="https://github.com/user-attachments/assets/c663cf85-b678-4306-976a-c3dd2e523d74" />


**Finished PCB**
a photo will be added here 

# LICENSE
This project is licensed under MIT License, check out [LICENSE](LICENSE) for more details. 
