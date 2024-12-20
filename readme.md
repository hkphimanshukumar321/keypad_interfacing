 APDLock: A Secure Locking Mechanism

## Overview

**APDLock** is a hardware module designed to securely control access using an FPGA/ASIC-based architecture. Leveraging the versatility of the Tiny Tapeout framework, this design ensures minimal latency, robust debouncing mechanisms, and clear digital interfacing for applications in keypad-based authentication systems.

---

## Features
- **Debounced Input Handling**: Ensures clean input signals by filtering noise.
- **Keypad Integration**: Compatible with the PmodKYPD keypad for user-friendly authentication.
- **Flexible Target Platforms**: Supports FPGA and ASIC implementations.
- **Minimal Resource Utilization**: Designed for efficient hardware resource consumption.
- **Visualization-Ready**: Integrated visual debugging support for Makerchip.

---

## Getting Started

### Prerequisites
1. **Tools**: 
   - Makerchip for simulation.
   - Yosys for synthesis.
   - FPGA programming tools (e.g., Xilinx Vivado or Intel Quartus).
2. **Hardware**: 
   - FPGA development board.
   - PmodKYPD keypad.
3. **Libraries**: 
   - Tiny Tapeout Library.

---

### File Structure
- **APDLock.tlv**: Top-level design file.
- **testbench.sv**: Testbench for simulation.
- **Makefile**: Automation script for build and simulation tasks.

---

### Simulation Instructions
1. Clone the repository:
   ```bash
   git clone <repository_url>
   cd APDLock
Run Makerchip simulation:
bash
Copy code
makerchip --file APDLock.tlv
Observe the waveform and verify button press behavior.
Synthesis and Implementation
Modify the target variable in APDLock.tlv to match your platform:
FPGA for FPGA synthesis.
ASIC for ASIC design flow.
Synthesize the design:
bash
Copy code
yosys -p "read_tlv APDLock.tlv; synth -top top; write_verilog APDLock.v"
Load the synthesized bitstream onto your FPGA.
Usage
Connect Hardware: Attach the PmodKYPD keypad to the designated pins on the FPGA board.
Power On: Apply power and observe system initialization via debug signals or LEDs.
Operate:
Press a button on the keypad to input a digit.
The module processes the input and outputs the digit code via the corresponding signal pins.
Key Parameters
Debouncing: Configurable via debounce_inputs parameter (1 for enabling, 0 for disabling).
Timing: Adjustable polling intervals using SeqWidth and SampleWidth variables.
Debugging
Enable visualization in Makerchip:
bash
Copy code
makerchip --file APDLock.tlv --debug
Examine signal transitions, button press detections, and debounce timings.
Contribution
Feel free to contribute to this project by submitting issues, feature requests, or pull requests. Follow the coding style outlined in the project guidelines.

