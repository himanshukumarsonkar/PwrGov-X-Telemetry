PwrGov-X — Telemetry-Driven Power Governor IP

PwrGov-X is a hardware IP core designed for dynamic power management in FPGA-based SoC systems. It monitors real-time execution telemetry (activity, stalls, memory access) and intelligently adjusts system power states to balance performance and energy efficiency.

This project implements a complete hardware-software co-design on a Zynq platform, where an ARM processor configures and interacts with the power governor IP via an AXI interface.

🎯 Key Features
⚡ Dynamic Power State Control
LOW_POWER
ACTIVE
TURBO
SLEEP
📊 Telemetry-Based Decision Making
Activity monitoring (valid, stall, mem_access)
Window-based utilization calculation
🧠 FSM-Based Control Logic
Threshold comparison
Hysteresis for stability
Deterministic transitions
🔌 AXI4-Lite Interface
CPU-configurable thresholds
Real-time status monitoring
🌟 Advanced (IP-Level Innovations)
🌡️ Thermal-Aware Control
Prevents TURBO mode under high temperature conditions
📈 Predictive Scaling
Detects rising workload trends before threshold crossing
🧩 Workload Classification
IDLE / COMPUTE / BURST / STALL_HEAVY classification
🏗️ System Architecture

The system consists of the following key modules:

Activity Monitor — Converts raw signals into activity pulses
Counter Block — Tracks active/stall cycles within a window
Utilization Calculator — Computes workload intensity
FSM Controller — Determines optimal power state
Control Signal Generator — Outputs clk_en and power_state
AXI Register Interface — Enables CPU interaction
🧪 FPGA Demonstration

The design is validated on a Zynq-based FPGA platform using UART output.

Test scenarios include:

Low activity → LOW_POWER
High activity → ACTIVE
Full utilization → TURBO
Stall conditions → SLEEP
Thermal throttling behavior
Predictive workload scaling
⚙️ Technology Stack
RTL: Verilog
EDA Tools: Vivado, Vitis
Platform: Zynq-7000 (ARM + FPGA)
Interface: AXI4-Lite
Software: Embedded C (Vitis)
📊 Performance Metrics

(Fill from your Vivado reports)

Frequency (Fmax): XXX MHz
LUT Usage: XXXX
FF Usage: XXXX
Power Consumption: X.XX W
📁 Repository Structure
PwrGov-X/
├── rtl/                # Verilog source files
├── tb/                 # Testbench
├── vivado/             # Vivado project files
├── vitis/              # Embedded software
├── docs/               # Architecture & design documents
├── demo/               # UART logs / demo outputs
├── reference_model/    # Python/C golden model
🧠 Design Philosophy

PwrGov-X is inspired by real-world DVFS (Dynamic Voltage and Frequency Scaling) techniques used in CPUs and SoCs. The goal is to bring hardware-level power intelligence into FPGA-based systems.

🏆 Achievements
Full hardware-software integration (ARM + FPGA)
Real-time adaptive power control
Modular, synthesizable RTL design
Extensible architecture for future innovations
📌 Future Work
Machine learning-based prediction
Multi-core workload balancing
Integration with OS-level schedulers
🤝 Contributors
Himanshu Kumar Sonkar, Saurabh Anand Jha, Prashant Kumar, Abu Zyan
