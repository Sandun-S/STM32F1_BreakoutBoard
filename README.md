# STM32F1 Breakout Board

This repository contains the schematic, PCB layout, and design files for a compact STM32F1 breakout board. It's designed to provide easy access to the core microcontroller features, USB connectivity, and a clean hardware interface for embedded projects.

## Features
- **Microcontroller**: STM32F103 series (ARM Cortex‑M3, up to 72 MHz)
- **Power Supply**:
  - USB-powered (5 V via Micro‑USB)
  - On-board 3.3 V regulator for VDD and VDDA
  - Decoupling and analog filtering components for stable operation
- **Clock**: External 8 MHz (or 16 MHz) crystal oscillator with load caps
- **USB Interface**:
  - USB D+ and D− routed as differential pair to MCU (PA11/PA12)
  - Optionally supports USB DFU or serial programming via USB
- **Boot, SWD, and Reset**:
  - BOOT0 and NRST header or pad access for programming and firmware recovery
  - SWD interface (SWDIO, SWCLK, GND, and optionally SWO)
- **I/O Accessibility**:
  - All available GPIOs broken out to standard 2.54 mm headers
  - Clear silkscreen labels for easy identification
- **PCB Design**:
  - Two-layer PCB with ground plane(s) and optimized layout for EMI performance
  - Designed with standard manufacturable dimensions for prototyping services like JLCPCB

## Contents
- `schematic/` – Electrical design (source files and exports)
- `pcb/` – PCB layout files (Gerber, drill, and 3D views)
- `BOM/` – Bill of materials listing required components
- `README.md` – This documentation

## Setup & Usage
1. Clone or download the repository.
2. Review the BOM and source files to understand component selection.
3. Customize the layout or schematic if adapting to a specific STM32F1 family variant (e.g. differing flash/RAM).
4. Export Gerbers and BOM for PCB fabrication and assembly.
5. Populate the board using standard SMD components and headers.
6. Program via SWD or USB DFU as supported by STM32 bootloader or ST-LINK.

## Customization Notes
- **MCU Variants**: Compatible with pin-compatible STM32F103 variants. Use datasheets to verify requirements such as flash size, timing, and voltage levels.
- **Power Supply**: Optionally bypass LDO or use external power—ensure proper VIN/USB isolation to avoid conflicts.
- **Boot Modes**: Use BOOT0 in combination with a reset to enter system bootloader for firmware updates via USB.

## Future Improvements
- Add user LEDs or buttons
- Expand support for lower-power STM32 variants
- Integrate USB host or CAN interface where applicable
