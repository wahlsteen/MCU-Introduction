# MCU-Introduction
This page introduces and compares some common microcontrollers 

---

# **AVR**

## **ATtiny85 – Minimalism and Control**

ATtiny85 is a classic 8-bit microcontroller from Microchip Technology (formerly Atmel), representing “old-school embedded” in its most concentrated form. It is built on the AVR architecture and runs at up to 20 MHz, though it is often used with the internal 8 MHz oscillator for simplicity.

What makes the ATtiny85 attractive is its simplicity and determinism. With only 8 kB of flash and 512 bytes of SRAM, it forces efficient coding, giving excellent control over timing and resource usage. It is well suited for small, dedicated tasks such as LED indicators, simple sensors, control logic, and battery-powered devices.

In terms of I/O, it is limited (6 GPIO), but still provides ADC, PWM, and basic communication via bit-banging or the USI module (a simplified SPI/I2C interface). It lacks native USB and is typically programmed via ISP, although bootloaders such as Digispark exist.

Its main strengths are low power consumption and minimal hardware requirements—it can run directly from a battery without additional circuitry. The downside is limited resources and a more manual workflow compared to modern microcontrollers.
<img src="https://res.cloudinary.com/rsc/image/upload/b_rgb:FFFFFF,c_pad,dpr_2.625,f_auto,h_214,q_auto,w_380/c_pad,h_214,w_380/F1331672-01?pgw=1" width=30%>

---

## **ATmega328P – The Arduino Reference**

ATmega328P from Microchip Technology is one of the most widely used microcontrollers ever, largely due to its role in the Arduino Uno. It is based on an 8-bit AVR architecture and typically runs at 16 MHz.

Its importance lies less in raw performance and more in its ecosystem. The Arduino platform has made it the default choice for education, prototyping, and hobby electronics. With 32 kB of flash and 2 kB of SRAM, it provides sufficient resources for a wide range of practical applications.

The ATmega328P offers a balanced set of peripherals: GPIO, 10-bit ADC, PWM, and communication interfaces such as SPI, I2C, and UART. Programming is usually done via a bootloader over UART/USB (through an adapter) or via ISP.

Its key strengths are stability, excellent documentation, and vast library support. However, it is beginning to show its age compared to modern 32-bit microcontrollers in both performance and memory capacity.

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/0c/ATMEGA328P-PU.jpg/1280px-ATMEGA328P-PU.jpg" width=30%>
---

## **LGT8F – An Enhanced AVR-Compatible Alternative**

LGT8F328P from LogicGreen is an AVR-compatible microcontroller often seen as an improved version of the ATmega328.

It maintains compatibility with the Arduino ecosystem, making it easy to integrate into existing projects. At the same time, it offers higher clock speeds (up to 32 MHz), improved ADC performance, and additional features compared to the original.

It is frequently available in DIP packages, making it convenient for breadboard prototyping. Programming can be done through the Arduino IDE using standard tools, which lowers the barrier to entry.

The main drawback is that compatibility is not always perfect. Some libraries and low-level functions may behave differently compared to a genuine ATmega device, which can introduce subtle issues.

Overall, it is an attractive option for users who want to stay within the Arduino ecosystem but gain additional performance and features.

<img src="https://modulshop.cdn.shoprenter.hu/custom/modulshop/image/cache/w900h500wt1q100/product/01%20Mikrovez%C3%A9rl%C5%91k/01%20Arduino/1-1-26_LGT8F328P_mini-3.jpg.webp?lastmod=0.1769439969" width=30%>
---

# **8051**

## **STC8G – A Modern 8051 in a Practical Package**

STC8G1K17 from STC Micro is a heavily modernized version of the 8051 architecture. Despite its heritage, it offers relatively high performance (up to ~35 MHz) and a surprisingly rich set of peripherals.

One of its key strengths is availability in DIP packages, making it highly attractive for prototyping and hobby projects without requiring advanced soldering. It includes ADC, PWM, timers, and a reasonable number of GPIO pins.

Programming is done via an integrated UART bootloader, allowing code upload without specialized hardware programmers. This simplifies the hardware setup but introduces a workflow that differs from more standardized platforms.

The ecosystem is more limited than that of ARM-based microcontrollers, and documentation can be inconsistent or less accessible.

Overall, the STC8G is a capable and practical microcontroller, particularly suited for low-cost and hardware-friendly applications.

---

## **CH552 – Low-Cost USB Microcontroller with 8051 Heritage**

CH552 from WCH is a modernized 8051-based microcontroller that remains highly relevant due to its integrated USB functionality. It runs at up to 24 MHz and offers significantly improved performance compared to traditional 8051 devices.

Its defining feature is the built-in USB controller, allowing it to function directly as a USB HID device (e.g., keyboard, mouse, or measurement tool) without external components. Combined with its extremely low cost, this makes it particularly attractive for small, specialized USB projects.

While its resources are limited (16 kB flash, 1 kB RAM), they are sufficient for many simple applications. It includes GPIO, ADC, and basic communication interfaces. Programming is done via a USB bootloader, eliminating the need for an external programmer.

The main limitation is the ecosystem. Toolchains, libraries, and documentation are less mature than those for ARM-based platforms, and debugging capabilities are more limited.

---

# **16-bit**

## **MSP430 – Ultra-Low Power Design**

MSP430 from Texas Instruments is designed with a clear goal: minimal power consumption. It is a 16-bit architecture typically operating at relatively low frequencies (1–25 MHz).

Its defining strength is energy efficiency. It features multiple advanced low-power modes and extremely fast wake-up times, making it ideal for battery-powered systems intended to operate for years.

The MSP430 includes ADC, timers, and standard communication interfaces such as SPI, I2C, and UART. However, the focus is on measurement and data acquisition rather than high computational performance.

Development is typically done using Texas Instruments’ tools (Code Composer Studio) or GCC-based alternatives. The ecosystem is stable but less hobby-oriented than Arduino or ESP platforms.

The main drawback is lower raw performance and a smaller community compared to more mainstream microcontrollers.

---

# **ARM**

## **SAMD21 – Modern Arduino on ARM**

ATSAMD21 from Microchip Technology is a 32-bit ARM Cortex-M0+ microcontroller used in modern Arduino boards such as the Zero and MKR series.

Running at up to 48 MHz, it offers significantly improved performance and flexibility compared to classic AVR devices. With 256 kB flash and 32 kB RAM, it supports more advanced applications and libraries.

A major advantage is native USB support, allowing it to act as a HID device without additional components. Its flexible SERCOM system enables dynamic configuration of communication interfaces (SPI, I2C, UART).

Programming can be done via the Arduino IDE or more advanced development environments, supporting both high-level and low-level approaches.

Its main limitation is that it is not as power-efficient as dedicated low-power microcontrollers, and some Arduino libraries are not fully optimized for it.

---

## **STM32 – A Flexible Industry Standard**

STM32 from STMicroelectronics is one of the most widely used microcontroller families in both industrial and advanced hobby applications.

The series ranges from simple Cortex-M0 devices to powerful Cortex-M7 processors. Its strength lies in the balance between performance, peripheral richness, and toolchain support. Many models feature high-quality ADCs, advanced timers, DMA, and strong real-time capabilities.

Development is commonly done using STM32CubeIDE with HAL libraries, which simplifies configuration. At the same time, developers can work directly with registers for full control. Debugging via SWD is highly capable.

The main drawback is complexity. The large product range and configuration options can be overwhelming, especially for beginners.

---

## **nRF52840 – Low-Power Wireless Precision**

nRF52840 from Nordic Semiconductor is a 32-bit ARM Cortex-M4 microcontroller optimized for wireless communication and low power consumption. It runs at up to 64 MHz and includes 1 MB flash and 256 kB RAM.

Its defining feature is its highly efficient and reliable Bluetooth Low Energy (BLE) implementation, making it ideal for battery-powered IoT devices, wearables, and sensor networks.

It also supports Thread and Zigbee, and includes a full set of peripherals such as GPIO, ADC, PWM, SPI, I2C, and USB. Programming is done via SWD or USB bootloader.

Its SDK (Nordic SDK, Zephyr RTOS) is powerful but more complex than Arduino-based environments. In return, it provides excellent control over power consumption and radio performance.

---

## **Raspberry Pi Pico (RP2040) – Flexible and Experimental**

Raspberry Pi Pico from Raspberry Pi Ltd is based on the RP2040, a dual-core ARM Cortex-M0+ microcontroller running at up to 133 MHz.

Its defining feature is flexibility. It includes two cores, 264 kB RAM, and programmable I/O (PIO) blocks that allow custom communication protocols to be implemented in hardware.

Programming is very user-friendly. Code can be uploaded via USB by simply copying a UF2 file. It supports both C/C++ and MicroPython.

Its main limitations are the lack of built-in wireless connectivity (except Pico W) and a relatively simple ADC.

---

# **RISC-V**

## **CH32V Series – RISC-V with STM32 Ambitions**

CH32V203 from WCH represents a family of microcontrollers designed to compete with STM32, but based on RISC-V instead of ARM.

They run up to ~144 MHz and offer a wide range of peripherals, including ADC, timers, DMA, and communication interfaces. On paper, they closely resemble STM32 devices.

Their main strength is cost efficiency. However, the ecosystem is less mature, with less polished tools and documentation.

---

## **ESP32-C6 – Modern Connected SoC**

ESP32-C6 from Espressif Systems is a modern 32-bit RISC-V microcontroller with integrated WiFi 6, Bluetooth LE, and Zigbee/Thread support.

Unlike simpler MCUs, it functions as a full system-on-chip, capable of running complex applications and RTOS environments. It includes extensive peripherals and is typically programmed via USB.

Its strengths are integration and connectivity, while its weaknesses include higher complexity and less deterministic behavior.

---

# 📊 **Translated Table**

| MCU           | Architecture | MHz    | Flash / RAM            | GPIO   | ADC       | Communication       | Power      | Form Factor | Programming    | Languages    | Connectivity      |
| ------------- | ------------ | ------ | ---------------------- | ------ | --------- | ------------------- | ---------- | ----------- | -------------- | ------------ | ----------------- |
| ATtiny85      | AVR (8-bit)  | 1–20   | 8 kB / 512 B           | 6      | 10-bit    | SPI, I2C            | Very low   | DIP         | ISP            | C/C++        | –                 |
| ATmega328P    | AVR (8-bit)  | 16     | 32 kB / 2 kB           | 23     | 10-bit    | SPI, I2C, UART      | Low        | DIP         | ISP/bootloader | C/C++        | –                 |
| LGT8F         | AVR-like     | 32     | 32 kB / 2 kB           | ~23    | 12-bit    | SPI, I2C, UART      | Low        | DIP         | ISP/Arduino    | C/C++        | –                 |
| STC8G         | 8051         | ~35    | ~8–64 kB / ~1–4 kB     | ~20    | 10–12 bit | UART, SPI, I2C      | Low        | DIP/SMD     | UART boot      | C            | –                 |
| CH552         | 8051         | 24     | 16 kB / 1 kB           | ~11    | 10-bit    | USB, SPI, UART      | Low        | SMD         | USB boot       | C            | USB               |
| MSP430        | 16-bit       | 1–25   | Varies                 | Varies | 10–12 bit | SPI, I2C, UART      | Very low   | DIP/SMD     | JTAG/SBW       | C            | –                 |
| SAMD21        | ARM M0+      | 48     | 256 kB / 32 kB         | ~20    | 12-bit    | SPI, I2C, UART, USB | Low        | SMD         | SWD/USB        | C/C++        | –                 |
| STM32         | ARM Cortex-M | 32–480 | Varies                 | Varies | 12–16 bit | SPI, I2C, UART, CAN | Low        | SMD         | SWD/JTAG       | C/C++        | –                 |
| nRF52840      | ARM M4       | 64     | 1 MB / 256 kB          | ~48    | 12-bit    | SPI, I2C, UART, USB | Very low   | SMD/module  | SWD/USB        | C/C++        | BLE, Thread       |
| RP2040 (Pico) | ARM M0+      | 133    | 2 MB / 264 kB          | 26     | 12-bit    | SPI, I2C, UART, USB | Low        | Module      | USB drag-drop  | C/Python     | –                 |
| CH32V         | RISC-V       | ~144   | ~64–256 kB / ~20–64 kB | ~30    | 12-bit    | SPI, I2C, UART      | Low–medium | SMD         | SWD            | C            | –                 |
| ESP32-C6      | RISC-V       | 160    | ~4 MB / ~400 kB        | ~20    | 12-bit    | SPI, I2C, UART, USB | Medium     | Module      | USB/UART       | C/C++/Python | WiFi, BLE, Zigbee |


