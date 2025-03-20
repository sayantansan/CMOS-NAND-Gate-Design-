# CMOS-NAND-Gate-Design-
Introduction to Magic VLSI
Magic is an open-source VLSI layout tool originally developed by John Ousterhout and his team at UC Berkeley. It is widely used for physical chip layout and runs primarily on Linux, though versions are available for other operating systems like DOS and OS/2. Magic is commonly used alongside IRSIM and other simulation tools.

For the latest version, visit:

Magic VLSI GitHub
Open Circuit Design
Cornell VLSI
Opening a Layout in Magic
Starting Magic: Layouts are stored in .mag files, with the first line specifying it as a Magic file.
Selecting a File: Go to File > Open and choose a .mag file (e.g., nandgate.mag).
Editing the Layout: Use the command window (tkcon 2.3 main) for modifications.
Further Tutorials: Magic Tutorials
CMOS NAND Gate
A 2-input CMOS NAND gate consists of two series NMOS transistors (between Y and Ground) and two parallel PMOS transistors (between Y and VDD).

If either input is 0, at least one NMOS transistor is OFF, allowing the PMOS network to pull Y high.
If both inputs are 1, the NMOS transistors conduct, pulling Y low.


Designing a CMOS NAND Gate in Magic
Below is a sample NAND gate layout:


Testing the NAND Gate with IRSIM
After designing the layout in Magic, the next step is testing the gate using IRSIM:

Extracting Layout Data:
Use the extract all command to generate a .ext file.
Convert it to a .sim file using ext2sim for IRSIM simulation.
IRSIM Overview
IRSIM is a switch-level digital circuit simulator that predicts circuit behavior using RC time constants. It works closely with Magic and reads .sim files.

IRSIM Commands
Set simulation step size: stepsize 50 (default is 10ns)
Define power and ground: h vdd, l gnd
Watch nodes: w a b output
Display node states: d
Set node low: l a, l b
Run simulation: s
Set node high: h a b
View waveforms: analyzer a b out
Important Notes
Nodes remain high or low until changed using the x command.
The IRSIM logic analyzer provides a graphical waveform view for analysis.
