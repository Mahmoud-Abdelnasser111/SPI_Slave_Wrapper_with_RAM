This project implements an SPI Slave connected to a Single-Port RAM capable of:

Receiving serial data through MOSI
Sending serial data through MISO
Writing data into RAM
Reading data from RAM
Handling SPI transactions using an FSM architecture

Three FSM encoding techniques were explored:

Sequential Encoding
Gray Encoding
One-Hot Encoding

The final implementation selects the encoding with the best timing performance after synthesis and implementation.

🛠️ Features
SPI Slave protocol implementation
FSM-based control unit
Single-Port RAM integration
Multiple FSM encoding techniques
Directed self-checking testbench
QuestaSim simulation flow using .do file
Vivado synthesis & implementation
Timing analysis and encoding comparison
Integrated debug core for internal signal monitoring
Bitstream generation
Lint-clean RTL

⚙️ System Description

The SPI Slave communicates with a master device through:

Signal	Description
MOSI	Master Output Slave Input
MISO	Master Input Slave Output
SS_n	Slave Select (Active Low)
clk	System Clock
rst_n	Active Low Reset

The slave supports:

RAM Write Operations
RAM Read Operations
State-controlled serial communication
Synchronous SPI transaction handling
🧠 FSM Encoding Exploration

The FSM implementation was synthesized using three encoding styles:

1️⃣ Sequential Encoding
Lower area utilization
Longer combinational paths
2️⃣ Gray Encoding
Reduced switching activity
Improved transition efficiency
3️⃣ One-Hot Encoding
Faster state transitions
Higher resource utilization

The final chosen encoding was based on:

Highest setup slack
Best hold timing
Highest achievable operating frequency after implementation
🧪 Verification Strategy

The testbench verifies:

Reset behavior
SPI state transitions
Write transactions to RAM
Read transactions from RAM
Correct serial shifting behavior
MISO output correctness
FSM transitions

Directed stimulus generation was used to validate different communication scenarios through the SPI interface.

▶️ Simulation
Run QuestaSim
do run.do

Simulation flow includes:

Library compilation
RTL compilation
Testbench execution
Waveform generation
Self-checking verification
🔍 Debug & Analysis

A debug core was added after selecting the best FSM encoding to monitor internal signals including:

MOSI
MISO
SS_n
rst_n
clk

This enables easier debugging and internal signal tracing on FPGA hardware.

🧩 Vivado Flow

The project was synthesized and implemented using Vivado including:

Elaboration
Synthesis
Implementation
Timing Analysis
Utilization Reports
Bitstream Generation

The design constraints connect:

rst_n, SS_n, and MOSI to switches
MISO to an LED
📊 Reports & Deliverables

The project includes:

RTL Design Files
Testbench
QuestaSim DO File
Constraint File (.xdc)
Generated Netlist
Bitstream File
Timing Reports
Utilization Reports
Schematic Snapshots
Critical Path Analysis
QuestaLint Reports
Waveform Screenshots

As required in the project deliverables.

📚 Concepts Covered
SPI Protocol
FSM Design
FSM Encoding Techniques
Verilog RTL Design
RAM Integration
FPGA Synthesis Flow
Timing Closure
Digital Verification
FPGA Debugging

👨‍💻 Tools Used
Verilog HDL
QuestaSim
Vivado
QuestaLint
📖 References

SPI Protocol Documentation
Xilinx Vivado Documentation
Digital Electronics Courses Material

✨ Author

Mahmoud Abdelnasser
Digital Design & Verification Engineer Enthusiast
