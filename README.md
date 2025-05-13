README.txt — Logic-Controlled Board Project

Purpose of the Project
----------------------
This project implements a Logic-Controlled Board that dynamically changes its LED activation sequence based on user interaction with physical switches. It uses a finite state machine (FSM) logic and timing behavior, including a 555 timer, to simulate intelligent LED behavior. The system supports both a Locked Mode (1-to-1 mapping) and an Unlocked Mode where the sequence is chosen based on the last switch turned OFF. It also includes a cap-removal trick to temporarily disable specific switches.

Directory Structure
-------------------
logic-lab-project/
|
├── Quartus_Project/           # All Quartus design files (.bdf, .v, .qsf, .sof)
│   ├── top_level.bdf
│   ├── sequence_controller.v
│   └── logic_board.qsf
|
├── Simulations/               # Testbenches or waveform outputs
│   └── logic_board_tb.vwf
|
├── Documentation/             # Project reports and LaTeX documentation
│   ├── report.pdf
│   └── bonus_555_timer_design.tex
|
├── Images/                    # Flowcharts, circuit diagrams
│   ├── flowchart_boot_sequence.png
│   ├── seq_logic_flowchart.png
│   └── 555_timer_astable.png
|
└── README.txt                 # This file

Included Files and Their Purpose
--------------------------------
- top_level.bdf: Main schematic entry for the board logic.
- sequence_controller.v: Verilog file implementing FSM and sequence selection logic.
- logic_board.qsf: Quartus settings file for project configuration.
- logic_board_tb.vwf: Testbench waveform used for simulation and verification.
- report.pdf: Contains the written analysis, results, and design explanation.
- bonus_555_timer_design.tex: LaTeX source file for the 555 Timer bonus documentation.
- 555_timer_astable.png: Circuit diagram used to configure LED ON-time with a 555 timer.
- flowchart images: Visual explanation of how the board determines sequences and manages transitions.

Setup and Usage Instructions
----------------------------
1. Open Quartus and load the projec]]t by opening 'logic_board.qsf'.
2. Compile the design and program the board using the .sof file.
3. Interact with the physical switches on your board:
   - If SW2 is ON, the board enters Locked Mode with fixed mappings.
   - If SW2 is OFF, the board starts in Sequence 1 and waits for switch interaction.
4. Observe the LED patterns change depending on which switch was last turned OFF.
5. Try the cap trick in SEQ3 to simulate switch disabling behavior.

Additional Design Insights
--------------------------
- The project’s main innovation lies in how it detects the last switch that was turned OFF and maps it to a corresponding LED sequence using a MUX and encoded logic.
- A 555 timer is used in astable mode to provide a 4-second delay, which controls transition timing and supports the switch disable trick.
- The design separates the physical switch input logic from the FSM output logic, improving modularity and reusability.
- We included both behavioral simulation (via waveform files) and physical testing (using soldered LEDs and breadboards).
