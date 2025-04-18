# 🎛️ Rotary Encoder Adventure with Altera MAX 2! 🌟

Welcome to the exciting world of rotary encoders! In this project, we’ll embark on a journey to interface a rotary encoder with the Altera MAX 2 CPLD, lighting up a dazzling sequence of 4 LEDs based on the twists and turns of our encoder. Whether you’re turning clockwise or anti-clockwise, the LEDs will follow your lead!

## 🚀 Features

- **Rotary Encoder Interface**: Detects your every twist and turn—clockwise or anti-clockwise!
- **LED Control**: Watch as 4 LEDs light up in a mesmerizing sequence based on your encoder's rotation.
- **FPGA Implementation**: Harness the power of the Altera MAX 2 CPLD to bring your design to life!

## 🛠️ Components Required

To get started on this electrifying project, you’ll need the following components:

1. **Altera MAX 2 Development Board**: Your trusty CPLD companion.
2. **Rotary Encoder**: The star of the show, with pins for GND, VCC, CLK (A), and DT (B).
3. **LED Module**: A vibrant collection of LEDs ready to shine!
4. **Power Supply**: 5V DC or whatever your board requires to keep the lights on.
5. **Programming Cable**: For uploading your masterpiece to the CPLD.

## 💡 Implementation

- **FPGA Board**: Altera MAX 2 EPM240T100C5N
- **Simulation Tool**: Altera Quartus II

## 🔌 Circuit Diagram

![Circuit Diagram](https://github.com/user-attachments/assets/d1b12d8d-8a16-47d4-9d2a-89fcbc128814)

### 📌 Pin Connections

## 📊 State Table

![State Table](https://github.com/Swara4600/Rotary_encoder/blob/main/state_rotary.png)

## 🖥️ Schematic Design

![Schematic Design](https://github.com/Swara4600/Rotary_encoder/blob/main/Screenshot%202025-04-09%20081106.png)

## 🔍 Simulation

We used Altera Quartus to create the schematic and verify that everything works like a charm! 

## 🚀 Programming the CPLD

Ready to bring your design to life? Follow these steps:

1. **Compile the Code**: Fire up Quartus II and compile your Verilog/VHDL code.
2. **Upload to CPLD**:
   - Connect your development board to your computer using the programming cable.
   - Use the Quartus II programmer to upload the compiled `.sof` file.
3. **Test the Circuit**:
   - Rotate the encoder clockwise and watch the LEDs light up in a dazzling sequence.
   - Rotate it anti-clockwise to see the LEDs reverse their dance!

## 🌟 Applications

- **Visual Feedback**: Perfect for user interfaces that need a little sparkle.
- **Educational Projects**: A fantastic way to learn about CPLD/FPGA interfacing.
- **Industrial Control Systems**: Bring your control systems to life with intuitive feedback!

## 🙏 Acknowledgments

A big shoutout to the Altera MAX II Development Board Documentation and the amazing community contributions on rotary encoder interfacing. Your support makes projects like this possible!

---

**Designed by**: Ketaki Bane  
**Project Type**: Digital Logic Design  
**Date**: April 2025

---

Join us on this journey of creativity and innovation! Happy coding! 🎉
