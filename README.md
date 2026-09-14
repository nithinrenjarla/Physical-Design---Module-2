# Physical-Design---Module-2
Power Integrity and Chip Floorplanning

# Project Overview
This project is part of the Physical Design (PD) learning journey and focuses on the fundamental concepts of ASIC Chip Floorplanning and Power Integrity.

The module explores how a logical netlist is transformed into a physical representation by defining the chip core and die dimensions, calculating cell area, setting utilization and aspect ratio, and organizing standard cells and pre-placed IP blocks within the floorplan.

The project also covers important power integrity concepts such as switching current, IR drop, inductive voltage drop, noise margin, and decoupling capacitors. In addition, practical aspects of the ASIC physical design flow are explored using the OpenLane flow, OpenROAD-based layout tools, and the SKY130 technology and standard-cell library.

The later stages of the module demonstrate floorplanning, power planning, PDN creation, standard-cell placement, placement blockages, tap cells, LEF and technology files, timing constraints, and binding logical netlist cells with physical library cells.

Overall, this project provides a step-by-step understanding of how an ASIC design progresses from a logical netlist to a structured physical layout.

# Table of Contents
1 - Define Width and Height of Core and Die 

2 - Convert Netlist Symbols into Physical Dimensions

3 - Calculate Area Occupied by the Netlist

4 - Utilization Factor and Aspect Ratio

5 - Core and Die Dimension Example

6 - Define Locations of Pre-placed Cells

7 - Placement of Pre-placed Cells

8 - IP Blocks and Floorplanning

9 - Surrounded Pre-Placed Cells with Decoupling Capacitors

10 - Switching Current and Voltage Drop

11 - Noise Margin

12 - Solution:Add Decoupling Capacitors

13 - Decoupling Capacitor Placement Around Blocks

14 - Decoupling Capacitor Placement in the Floorplan

15 - Power Network,Driver,Load and 16-bit Bus

16 - Floorplanning

17 - Power Planning

18 - Power Distribution Network

19 - Picorv32a ASIC Design Flow using OpenLane

20 - OpenLane Physical Design Configuration

21 - SkyWater PDK LEF File Configuration

22 - OpenLane Floorplanning Configuration

23 - Standard Cell Placement

24 - Decoupling Capacitors

25 - Logical Cell Placement Blockage

26 - Tap Cells

27 - LEF & Technology Files

28 - OpenLane Configuration

29 - Timing Constraints

30 - OpenROAD / Layout View

31 - Bind Netlist with Physical Library Cells

32 - Placement

# Tools and Technologies

| Tool / Technology |	Purpose |
|---|---|
| **OpenLane** | Automated open-source RTL-to-GDSII ASIC design flow |
| **OpenROAD** | Physical design implementation and layout visualization |
| **SKY130 PDK** |	Open-source 130 nm process design kit |
| **sky130_fd_sc_hd** |	High-density standard-cell library |
| **LEF Files**	|Physical abstraction of standard cells, pins, layers, and obstructions |
| **Tcl** |	Configuration and automation of the OpenLane flow |
| **Verilog** |	Hardware description of the design |
| **SDC** |	Timing and clock constraint definition |
| **KLayout / Layout Viewer** |	Visualization and inspection of physical layouts |
| **Linux / Ubuntu** |	Development and execution environment |
| **GitHub** |	Project documentation and version control |

# 1. Define Width and Height of Core and Die
The first step in physical design is to understand the netlist and convert the logical representation of the design into physical dimensions.

A netlist describes the connectivity between different components of an electronic design.

The example netlist contains:

Flip-Flops (FF)
AND gate
OR gate
Clock connection
Data connections
The standard cells and flip-flops in the netlist are later converted into physical dimensions during floorplanning.


# 2. Convert Netlist Symbols into Physical Dimensions
After understanding the netlist, the logical components are represented as physical standard cells.

The highlighted elements include:

Flip-Flops
Standard cells
AND/OR logic cells
Each logical cell occupies a certain physical area on the silicon.

Therefore, the total area occupied by all cells must be calculated before determining the core dimensions.


# 3. Calculate Area Occupied by the Netlist
For the given example, each standard cell and flip-flop is represented as a unit square.

For example:
``` text 
Width  = 1 unit
Height = 1 unit

Area = Width × Height
     = 1 × 1
     = 1 sq. unit
```
The total area occupied by the netlist is calculated by adding the area of all standard cells and flip-flops. This gives the total cell area required inside the core.


# 4. Utilization Factor and Aspect Ratio
Two important parameters used to define the core dimensions are: Utilization Factor
```text
Utilization Factor =
Area Occupied by Netlist
-------------------------
Total Area of Core
```
Screenshot (120)
The utilization factor indicates how much of the core area is occupied by the placed cells. Aspect Ratio Aspect Ratio = Height / Width For the example shown, the core and die dimensions are selected based on the required utilization factor and aspect ratio. The diagram illustrates a core of approximately 4 units × 2 units with the die surrounding the core.

