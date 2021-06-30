# Advanced Physical Design Using OpenLANE/Sky130

![workshop_banner](https://user-images.githubusercontent.com/86701156/123913967-7b330980-d99c-11eb-81cf-37c61edde8c7.JPG)

## Table of Contents

## About
This project documents learnings from the Advanced Physical Design Workshop using OpenLANE/Sky130 conducted by VLSI System Design. OpenLANE is an opensource tool or flow used for opensource tape-outs. The OpenLANE flow comprises a variety of tools such as Yosys, ABC, OpenSTA, Fault, OpenROAD app, Netgen and Magic which are used to harden chips and macros, i.e. generate final GDSII from the design RTL. The primary goal of OpenLANE is to produce clean GDSII with no human intervention. OpenLNE has been tuned to function for the Google-Skywater130 Open Process Design Kit.

## Day1: Inception of Opensource EDA, OpenLANE and Sky130 PDK

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








