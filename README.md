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

<img width="820" height="551" alt="image" src="https://github.com/user-attachments/assets/7da8b4fe-1532-45b8-8169-103e7a9ab2e3" />

**3d Render**

<img width="746" height="496" alt="image" src="https://github.com/user-attachments/assets/bad14564-1b72-40f7-a6c2-1fb9b49b727e" />


**Finished PCB**
a photo will be added here 

# LICENSE
This project is licensed under MIT License, check out [LICENSE](LICENSE) for more details. 
