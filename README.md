# Advanced Physical Design Using OpenLANE/Sky130

![workshop_banner](https://user-images.githubusercontent.com/86701156/123913967-7b330980-d99c-11eb-81cf-37c61edde8c7.JPG)

## Table of Contents
1. [About](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#about)
2. [Day 1: Inception of Opensource EDA](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#day-1-inception-of-opensource-eda)
   - [How to Talk to computers?](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#how-to-talk-to-computers)
   - [SOC Design & OpenLANE](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#soc-design--openlane)
     - [Components of opensource digital ASIC design](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#components-of-opensource-digital-asic-design)
     - [Simplified RTL2GDS Flow](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#simplified-rtl2gds-flow)
     - [OpenLANE ASIC Flow](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#openlane-asic-flow)
   - [Opensource EDA tools](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#opensource-eda-tools)
     - [OpenLANE Files](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#openlane-files)
     - [Invoking OpenLANE](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#invoking-openlane)
     - [Design Preparation Step](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#design-preparation-step)
     - [Review of files & Synthesis step](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#design-preparation-step#review-of-files-&-synthesis-step)
     - [Characterization of synthesis results](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#characterization-of-synthesis-results)
3. [Day 2: Floorplanning and library cells](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#day-2-floorplanning-and-library-cells)
   - [Floorplanning considerations](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#floorplanning-considerations)
     - [Utilization Factor & Aspect Ratio](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#utilization-factor--aspect-ratio)
     - [Pre-placed cells](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#pre-placed-cells)
     - [Decoupling capacitors](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#decoupling-capacitors)
     - [Power Planning](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#power-planning)
     - [Pin Placement](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#pin-placement)
     - [Floorplan run on OpenLANE & view in Magic](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#floorplan-run-on-openlane--view-in-magic)
   - [Placement](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#placement)
     - [Placement Optimization](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#placement-optimization)
     - [Placement run on OpenLANE & view in Magic](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#placement-run-on-openlane--view-in-magic)
   - [Standard Cell Design Flow](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#standard-cell-design-flow)
   - [Standard Cell Characterization Flow](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#standard-cell-characterization-flow)
   - [Timing Parameter Definitions](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#timing-parameter-definitions)
4. [Day 3: Design library cell](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#day-3-design-library-cell)
   - [SPICE Deck creation & Simulation](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#spice-deck-creation--simulation)
   - [CMOS inverter Switching Threshold Vm](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#cmos-inverter-switching-threshold-vm)
   - [16 Mask CMOS Fabrication](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#16-mask-cmos-fabrication)
   - [Inverter Standard cell Layout & SPICE extraction](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#inverter-standard-cell-layout--spice-extraction)
   - [Inverter Standard cell characterization](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#inverter-standard-cell-characterization)
   - [Magic Features & DRC rules](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#magic-features--drc-rules)
5. [Day 4: Timing Analysis & CTS](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#day-4-timing-analysis--cts)
   - [Standard Cell LEF generation](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#standard-cell-lef-generation)
   - [Integrating custom cell in OpenLANE](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#integrating-custom-cell-in-openlane)
   - [Post-synthesis timing analysis](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#post-synthesis-timing-analysis)
   - [Clock Tree Synthesis](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#clock-tree-synthesis)
6. [Day 5: Final steps in RTL2GDS](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#day-5-final-steps-in-rtl2gds)
   - [Power Distribution Network generation](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#power-distribution-network-generation)
   - [Routing](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#routing)
9. [Future Scope](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#future-scope)
10. [Acknowledgements](https://github.com/aasthadave9/Advanced-Physical-Design-Using-OpenLANE-Sky130/blob/main/README.md#acknowledgements)

## About
OpenLANE is an opensource tool or flow used for opensource tape-outs. The OpenLANE flow comprises a variety of tools such as Yosys, ABC, OpenSTA, Fault, OpenROAD app, Netgen and Magic which are used to harden chips and macros, i.e. generate final GDSII from the design RTL. The primary goal of OpenLANE is to produce clean GDSII with no human intervention. OpenLANE has been tuned to function for the Google-Skywater130 Open Process Design Kit.

## Day 1: Inception of Opensource EDA

### How to talk to computers?
The RISC-V Instruction Set Architecture (ISA) is a language used to talk to computers whose hardware is based on RISC-V core. If a user wishes to run a certain application software on a computer, its corresponding C/C++/Java program must be converted into instructions by the compliler. The ouput of the compiler is hardware dependent. These instructions go as inputs to the assembler which outputs binary language that the hardware logic in the chip layout can make sense of. According the the bits received, the digital logic consisting of gates performs the function required by the user of the application software.

### SoC Design & OpenLANE

#### Components of opensource digital ASIC design
The design of digital Application Specific Integrated Circuit (ASIC) requires three enablers or elements - Resistor Transistor Logic Intellectual Property (RTL IPs), Electronic Design Automation (EDA) Tools and Process Design Kit (PDK) data.

![ASIC](https://user-images.githubusercontent.com/86701156/124005001-35a32a80-d9f6-11eb-8fcc-0917ad337699.PNG)
- Opensource RTL Designs: github, librecores, opencores
- Opensource EDA tools: QFlow, OpenROAD, OpenLANE
- Opensource PDK data: Google Skywater130 PDK

The ASIC flow objective is to convert RTL design to GDSII format used for final layout. The flow is essentially a software also known as automated PnR (Place & route).

#### Simplified RTL2GDS Flow
![RTL2GDS flow](https://user-images.githubusercontent.com/86701156/124006238-a139c780-d9f7-11eb-8da9-6069b055fbe0.PNG)

- Synthesis: RTL Converted to gate level netlist using standard cell libraries (SCL)
- Floor & Power Planning: Planning of silicon area to ensure robust power distribution
- Placement: Placing cells on floorplan rows aligned with sites
  - Global Placement: for optimal position of cells
  - Detailed Placement: for legal positions
- Routing: Valid patterns for wires
- Signoff: Physical (DRC, LVS) and Timing verifications (STA)

#### OpenLANE ASIC Flow
![openlane asic flow](https://user-images.githubusercontent.com/86701156/124007394-f62a0d80-d9f8-11eb-9d46-7cc885c0eff6.PNG)
### Opensource EDA tools
OpenLANE utilises a variety of opensource tools in the execution of the ASIC flow:
Task | Tool/s
------------ | -------------
RTL Synthesis & Technology Mapping | [yosys](https://github.com/YosysHQ/yosys), abc
Floorplan & PDN | init_fp, ioPlacer, pdn and tapcell
Placement | RePLace, Resizer, OpenPhySyn & OpenDP
Static Timing Analysis | [OpenSTA](https://github.com/The-OpenROAD-Project/OpenSTA)
Clock Tree Synthesis | [TritonCTS](https://github.com/The-OpenROAD-Project/OpenLane)
Routing | FastRoute and [TritonRoute](https://github.com/The-OpenROAD-Project/TritonRoute) 
SPEF Extraction | [SPEF-Extractor](https://github.com/HanyMoussa/SPEF_EXTRACTOR)
DRC Checks, GDSII Streaming out | [Magic](https://github.com/RTimothyEdwards/magic), [Klayout](https://github.com/KLayout/klayout)
LVS check | [Netgen](https://github.com/RTimothyEdwards/netgen)
Circuit validity checker | [CVC](https://github.com/d-m-bailey/cvc)


#### OpenLANE Files

The openLANE file structure looks something like this:

![lab1](https://user-images.githubusercontent.com/86701156/124007834-633da300-d9f9-11eb-8b32-9c1624019f29.PNG)
![lab2](https://user-images.githubusercontent.com/86701156/124007858-69338400-d9f9-11eb-9e98-cec32e28b01f.PNG)
![lab3](https://user-images.githubusercontent.com/86701156/124007881-6f296500-d9f9-11eb-87ff-a0a5ede3c07a.PNG)

- skywater-pdk: contains PDK files provided by foundry
- open_pdks: contains scripts to setup pdks for opensource tools 
- sky130A: contains sky130 pdk files

#### Invoking OpenLANE
Openlane can be invoked using docker command followed by opening an interactive session.
flow.tcl is a script that specifies details for openLANE flow.

```
docker
./flow.tcl -interactive
package require openlane 0.9
```
![lab4](https://user-images.githubusercontent.com/86701156/124007900-75b7dc80-d9f9-11eb-83d9-b8998859afb0.PNG)

#### Design Preparation Step
 Various packages are initialized followed by preparation of the picorv32a design.
 ```
 prep -design picorv32a
 ```
![lab5](https://user-images.githubusercontent.com/86701156/124008828-7dc44c00-d9fa-11eb-989e-1f699bc97572.PNG)
![lab6](https://user-images.githubusercontent.com/86701156/124009124-d7c51180-d9fa-11eb-92b1-4171ead9b2d7.PNG)

#### Review of files & Synthesis step
A "runs" folder is generated within the picorv32a folder.

![lab7](https://user-images.githubusercontent.com/86701156/124009377-270b4200-d9fb-11eb-957f-4f73c5baf8dc.PNG)

Since today's date is 30th June, a folder titled "30-06..." is created within the picorv32a directory:

![lab9](https://user-images.githubusercontent.com/86701156/124009563-63d73900-d9fb-11eb-8f37-fcdd43f46092.PNG)

The merged file is created during the merging operation in the pircorv32a design preparation (it merges lef and techlef files)

![lab10](https://user-images.githubusercontent.com/86701156/124009626-75204580-d9fb-11eb-945f-48b1510d45f4.PNG)

Merged.lef looks something like this:

![lab11](https://user-images.githubusercontent.com/86701156/124009634-781b3600-d9fb-11eb-91ce-053c814592d0.PNG)

Next, we run the synthesis of picorv32a design in the openlane interactive terminal:
`run_synthesis`

![lab14](https://user-images.githubusercontent.com/86701156/124010076-fd064f80-d9fb-11eb-87a1-d66b99de9cd2.PNG)

The yosys and ABC tools are utilised to convert RTL to gate level netlist

![lab15](https://user-images.githubusercontent.com/86701156/124010081-fed01300-d9fb-11eb-844e-7056cbadf592.PNG)

Calcuation of Flop Ratio:
Flop ratio equals the Number of D Flip flops divided by Total Number of cells. 

![lab16](https://user-images.githubusercontent.com/86701156/124060928-9c9efe80-da4b-11eb-9b4a-353390683bfa.PNG) ![lab17](https://user-images.githubusercontent.com/86701156/124060933-9f99ef00-da4b-11eb-887f-ddd54e269afa.PNG)

dfxtp_4 = 1613,
Number of cells = 14876,
Therefore, Flop ratio = 1613/14876 = 0.1084 = 10.84%

#### Characterization of synthesis results
We may check the success of the synthesis step by checking the synthesis folder for the synthesised netlist file (.v file)
![lab18](https://user-images.githubusercontent.com/86701156/124061491-8e051700-da4c-11eb-9212-d26b4ca25595.PNG)

The synthesis statistics report can be accessed within the reports directory. It is usually the last yosys file since files are listed chronologically by date of modification

![lab19](https://user-images.githubusercontent.com/86701156/124061967-7da16c00-da4d-11eb-8bf0-bf18b11e612c.PNG)![lab20](https://user-images.githubusercontent.com/86701156/124062667-ba219780-da4e-11eb-938e-88fc3e2997cb.PNG)

## Day 2: Floorplanning and library cells

### Floorplanning considerations

#### Utilization Factor & Aspect Ratio  

Two parameters are of importance when it comes to floorplanning namely, Utilisation Factor and Aspect Ratio. They are defined as follows:

```
Utilisation Factor =  Area occupied by netlist/ Total area of core

```

```
Aspect Ratio = Height/ Width

```
                                  
A Utilisation Factor of 1 signifies 100% utilisation leaving no space for extra cells such as buffer. However, practically, the Utilisation Factor is 0.5-0.6. Likewise, an Aspect ratio of 1 implies that the chip is square shaped. Any value other than 1 implies rectanglular chip.

#### Pre-placed cells

Once the Utilisation Factor and Aspect Ratio has been decided, the locations of pre-placed cells need to be defined. Pre-placed cells are IPs comprising large combinational logic which once placed maintain a fixed position. Since they are placed before placement and routing, the are known as pre-placed cells.

#### Decoupling capacitors

Pre-placed cells must then be surrounded with decoupling capacitors (decaps). The resistances and capacitances associated with long wire lengths can cause the power supply voltage to drop significantly before reaching the logic circuits. This can lead to the signal value entering into the undefined region, outside the noise margin range.  Decaps are huge capacitors charged to power supply voltage and placed close the logic circuit. Their role is to decouple the circuit from power supply by supplying the necessary amount of current to the circuit. They pervent crosstalk and enable local communication

#### Power Planning

Each block on the chip, however, cannot have its own decap unlike the pre-placed macros. Therefore a good power planning ensures that each block has its own VDD and VSS pads connected to the horizontal and vertical power and GND lines which form a power mesh.

#### Pin Placement

The netlist defines connectivity between logic gates. The place between the core and die is utilised for placing pins. The connectivity information coded in either VHDL or Verilog is used to determine the position of I/O pads of various pins. Then, logical placement blocking of pre-placed macros is performed so as to differentiate that area from that of the pin area.

#### Floorplan run on OpenLANE & view in Magic

Files of importance in increasing priority order:
1. ```floorplan.tcl``` - System default envrionment variables
2. ```conifg.tcl```
3. ```sky130A_sky130_fd_sc_hd_config.tcl```

![floorplan tcl file (system default)](https://user-images.githubusercontent.com/86701156/124388831-398ac180-dd02-11eb-9f2b-b950fa8adaa9.PNG)
![config tcl file](https://user-images.githubusercontent.com/86701156/124388834-3bed1b80-dd02-11eb-9b81-eb0a4fa3a55c.PNG)
![sky130 tcl file](https://user-images.githubusercontent.com/86701156/124388839-40193900-dd02-11eb-8545-ab568e51f315.PNG)

Floorplan envrionment variables or switches:
1. ```FP_CORE_UTIL``` - floorplan core utilisation
2. ```FP_ASPECT_RATIO``` - floorplan aspect ratio
3. ```FP_CORE_MARGIN``` - Core to die margin area
4. ```FP_IO_MODE``` - defines pin configurations (1 = equidistant/0 = not equidistant)
5. ```FP_CORE_VMETAL``` - vertical metal layer
6. ```FP_CORE_HMETAL``` - horizontal metal layer

***Note: Usually, vertical metal layer and horizontal metal layer values will be 1 more than that specified in the files***
 
 To run the picorv32a floorplan in openLANE:
 ```
 run_floorplan
 
 ```
 ![floorplan run step](https://user-images.githubusercontent.com/86701156/124388819-2c6dd280-dd02-11eb-81b5-fb9d0c7f9141.PNG)

Post the floorplan run, a .def file will have been created within the ```results/floorplan``` directory. We may review floorplan files by checking the ```floorplan.tcl```. The system defaults will have been overriden by switches set in ```conifg.tcl``` and further overriden by switches set in ```sky130A_sky130_fd_sc_hd_config.tcl```.
 
To view the floorplan, Magic is invoked after moving to the ```results/floorplan``` directory:
```
magic -T /home/aastha/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &

```

   ![magic layout](https://user-images.githubusercontent.com/86701156/124388970-cafa3380-dd02-11eb-86ca-64739139683d.PNG)
 
One can zoom into Magic layout by selecting an area with left and right mouse clcik followed by pressing "z" key. Here, equidistant input pins (FP_IO_MODE = 1) can be viewed:
 
   ![equidistant input ports](https://user-images.githubusercontent.com/86701156/124389036-05fc6700-dd03-11eb-930f-4452652a0a09.PNG)
 
Various components can be identified by using the ```what``` command in tkcon window after making a selection on the component:

   ![selected input port - metal layer2](https://user-images.githubusercontent.com/86701156/124389094-4c51c600-dd03-11eb-927b-56a129e5f08b.PNG)

Zooming in also provides a view of decaps present in picorv32a chip:

   ![decap-decoupling capacitor](https://user-images.githubusercontent.com/86701156/124389047-1876a080-dd03-11eb-90bc-ae28b2fea211.PNG)

The standard cell can be found at the bottom left corner:

   ![standard cell at left bottom corner](https://user-images.githubusercontent.com/86701156/124389059-275d5300-dd03-11eb-9327-116abf31cd6c.PNG)


### Placement 

#### Placement Optimization

The next step in the OpenLANE ASIC flow is placement. The synthesized netlist is the be placed on the floorplan. Placement is perfomed in 2 stages:

1. Global Placement: It finds optimal position for all cells which may not be legal and cells may overlap. Optimization is done through reduction of half parameter wire length
2. Detailed Placement: It alters the position of cells post global placement so as to legalise them

Legalisation of cells is important from timing point of view. 

#### Placement run on OpenLANE & view in Magic

Congestion aware placement using RePIAce:
```
run_placement

```
The objective of placement is the convergence of overflow value. If overflow value progressively reduces during the placement run it implies that the design will converge and placement will be successful. Post placement, the design can be viewed on magic within ```results/placement``` directory:

```
magic -T /home/aastha/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &

```
![layout after placement](https://user-images.githubusercontent.com/86701156/124393474-54683080-dd18-11eb-95c1-31d75e514623.PNG)

Zoomed-in views of the standard cell placement:

![zoomed in view of std cell placement](https://user-images.githubusercontent.com/86701156/124393477-57632100-dd18-11eb-8983-64301d0a6cc3.PNG)
![zoomed in view of std cell placement2](https://user-images.githubusercontent.com/86701156/124393481-5af6a800-dd18-11eb-91b2-a52e072dfb0d.PNG)

***Note: Power distribution network generation is usually a part of the floorplan step. However, in the openLANE flow, floorplan does not generate PDN. The steps are - floorplan, placement CTS and then PDN***


### Standard Cell Design Flow

Standard cell design flow involves the following:
1. Inputs: PDKs, DRC & LVS rules, SPICE models, libraries, user-defined specifications 
2. Design steps: Circuit design, Layout design (Art of layout Euler's path and stick diagram), Extraction of parasitics, Characterization (timing, noise, power)
3. Outputs: CDL (circuit description language), LEF, GDSII, extracted SPICE netlist (.cir), timing, noise and power .lib files

### Standard Cell Characterization Flow

A typical standard cell characterization flow includes the following steps:
1. Read in the models and tech files
2. Read extracted spice netlist
3. Recognise behaviour of the cell
4. Read the subcircuits
5. Attach power sources
6. Apply stimulus to characterization setup
7. Provide necessary output capacitance loads
8. Provide necessary simulation commands

The opensource software called GUNA can be used for characterization. Steps 1-8 are fed into the GUNA software which generates timing, noise and power models.

### Timing Parameter Definitions

Timing defintion | Value
------------ | -------------
slew_low_rise_thr  | 20% value
slew_high_rise_thr |  80% value
slew_low_fall_thr | 20% value
slew_high_fall_thr | 80% value
in_rise_thr | 50% value
in_fall_thr | 50% value
out_rise_thr | 50% value
out_fall_thr | 50% value

```
rise delay =  time(out_fall_thr) - time(in_rise_thr)

Fall transition time: time(slew_high_fall_thr) - time(slew_low_fall_thr)

Rise transition time: time(slew_high_rise_thr) - time(slew_low_rise_thr)
```

A poor choice of threshold points leads to neative delay value. Therefore a correct choice of thresholds is very important

## Day 3: Design library cell

OpenLANE allows users to make changes to environment variables on the fly. For instance, if we wish to change the pin placement from equidistant to some other style of placement we may do the following in the openLANE flow:
```
set ::env(FP_IO_MODE) 2
```

### SPICE Deck creation & Simulation

A SPICE deck includes information about the following:
1. Model description
2. Netlist description
3. Component connectivity
4. Component values
5. Capacitance load
6. Nodes
7. Simulation type and parameters
8. Libraries included

### CMOS inverter Switching Threshold Vm

Thw sitching threshold of a CMOS inverter is the point on the transfer characteristic where Vin equals Vout (=Vm). At this point both PMOS and NOMOS are in ON state which gives rise to a leakage current

### 16 Mask CMOS Fabrication
The 16-mask CMOS process consists of the following steps:
1. Selection of subtrate
2. Creating active region for transistors
3. N-well and P-well formation
4. Formation of gate terminal
5. LDD (lightly doped drain) formation
6. Source & drain formation
7. Local interconnect formation
8. Higher level metal formation

### Inverter Standard cell Layout & SPICE extraction


### Inverter Standard cell characterization

### Magic Features & DRC rules

## Day 4: Timing Analysis & CTS

### Standard Cell LEF generation

### Integrating custom cell in OpenLANE

### Post-synthesis timing analysis

### Clock Tree Synthesis

## Day 5: Final steps in RTL2GDS

### Power Distribution Network generation

### Routing 

## Future Scope

## References 
- [The OpenROAD Project](https://github.com/The-OpenROAD-Project/OpenLane)
- [Nickson Jose](https://github.com/nickson-jose/vsdstdcelldesign)
- [Kunal Ghosh](https://github.com/kunalg123)
 







