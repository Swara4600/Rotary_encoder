
# Rotary Encoder with Altera MAX 2 (Controlling LEDs)

This project demonstrates how to interface a rotary encoder with the Altera MAX 2 CPLD to control the state of 4 LEDs. The LEDs will light up in a sequence based on the rotation of the encoder, either clockwise or anti-clockwise.

---

## Features

- **Rotary Encoder Interface**: Detects clockwise and anti-clockwise rotation.
- **LED Control**: Updates the state of 4 LEDs based on the encoder's rotation.
- **FPGA Implementation**: Implements the functionality using Altera MAX 2 CPLD.

---

## Components Required

1. **Altera MAX 2 Development Board**: CPLD used for processing.
2. **Rotary Encoder**: With pins for GND, VCC, CLK (A), and DT (B).
3. **LED module**: LEDs modules having multiple LED's.
5. **Power Supply**: 5V DC or as required by the development board.
6. **Programming Cable**: For uploading the compiled design to the CPLD.

---

## Circuit Diagram
![Alt Text](https://app.diagrams.net/#G1BKfS8M5c6pZoAbiBCce9VmJtt2dy0loa#%7B%22pageId%22%3A%22RVINTYbqA5r6dPPLfOth%22%7D)
```
Rotary Encoder:
  CLK -> CPLD Pin 1
  DT  -> CPLD Pin 2
  VCC -> 3.3V or 5V
  GND -> GND

LEDs:
  LED1 -> CPLD Pin 57 
  LED2 -> CPLD Pin 61
  LED3 -> CPLD Pin 67
  LED4 -> CPLD Pin 69

```

---

## Code Description

### VHDL/Verilog Design

The design uses a finite state machine (FSM) to detect the rotation direction of the encoder and updates the LEDs accordingly.

### Example Code (Verilog)

```verilog
module rotary_encoder_led_control(
    input clk,         // System clock
    input reset,       // Reset signal
    input encoder_a,   // Rotary encoder A (CLK)
    input encoder_b,   // Rotary encoder B (DT)
    output reg [3:0] leds // 4 LEDs
);

    reg [1:0] state; // To track rotation state

    always @(posedge clk or posedge reset) begin
        if (reset) begin
            leds <= 4'b0001; // Initialize with LED1 ON
            state <= 2'b00;
        end else begin
            state <= {encoder_a, encoder_b}; // Capture encoder state

            case (state)
                2'b01: leds <= {leds[2:0], leds[3]}; // Clockwise rotation
                2'b10: leds <= {leds[0], leds[3:1]}; // Anti-clockwise rotation
                default: leds <= leds; // No change
            endcase
        end
    end
endmodule
```

---

## Simulation

Use a simulation tool like ModelSim to verify the functionality of the Verilog/VHDL code. Simulate the input signals (`encoder_a` and `encoder_b`) to ensure proper LED transitions.

---

## Programming the CPLD

1. **Compile the Code**: Use Quartus II software to compile the Verilog/VHDL code.
2. **Upload to CPLD**:
   - Connect the development board to your computer using the programming cable.
   - Use the Quartus II programmer to upload the compiled `.sof` file.
3. **Test the Circuit**:
   - Rotate the encoder clockwise to see the LEDs light up in sequence.
   - Rotate it anti-clockwise to see the LEDs reverse the sequence.

---

## Applications

- Visual feedback for user interfaces.
- Educational projects for learning CPLD/FPGA interfacing.
- Industrial control systems.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Acknowledgments

- Altera MAX II Development Board Documentation
- Community contributions on rotary encoder interfacing
