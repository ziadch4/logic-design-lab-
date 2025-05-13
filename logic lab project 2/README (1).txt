README.txt – Logic-Controlled Board Project

What This Project Is About
--------------------------
This project is called the Logic-Controlled Board. It’s a system that lights up LEDs in different sequences based on how you interact with switches. It has two modes:

- Locked Mode: each switch controls its own LED directly.
- Unlocked Mode: the board chooses a pattern (sequence) based on the last switch that was turned OFF.

We also used a 555 timer to help control how long certain actions last (like turning LEDs ON for a few seconds).

What’s Inside This Project Folder
---------------------------------
logic-lab-project/
|
├── Quartus_Project/       → All the circuit design files (used in Quartus)
├── Simulations/           → Test files to check if the circuit works
├── Documentation/         → Report and bonus work
├── Images/                → Flowcharts and diagrams
└── README.txt             → This file

Quick Description of the Files
------------------------------
- top_level.bdf → The main design made with blocks in Quartus  
- sequence_controller.v → The part that controls the LED sequences  
- logic_board.qsf → The project setup file for Quartus  
- logic_board_tb.vwf → A test file to see how the circuit behaves  
- report.pdf → Our written explanation of the project  
- bonus_555_timer_design.tex → LaTeX file showing how we used the 555 timer  
- flowchart_*.png → Diagrams showing how the board works  
- 555_timer_astable.png → The 555 timer circuit we built

How to Use This Project
-----------------------
1. Open the Quartus software.
2. Load the project by opening 'logic_board.qsf'.
3. Compile the project.
4. Upload it to the board.
5. Use the switches:
   - If SW2 is ON, it’s in Locked Mode.
   - If SW2 is OFF, it’s in Unlocked Mode, and the last switch you turned OFF chooses the LED pattern.
6. In one special pattern, if you turn off a switch and leave it OFF for 4 seconds, it gets "disabled" temporarily.

Why This Project Is Cool
------------------------
- It changes how LEDs light up based on what the user does.
- It remembers which switch was last used.
- It uses a real hardware trick (the cap trick) to surprise the user.
- The 555 timer helps keep timing accurate.
