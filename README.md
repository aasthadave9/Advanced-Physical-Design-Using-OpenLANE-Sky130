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

#### OpenLANE Files
![lab1](https://user-images.githubusercontent.com/86701156/124007834-633da300-d9f9-11eb-8b32-9c1624019f29.PNG)
![lab2](https://user-images.githubusercontent.com/86701156/124007858-69338400-d9f9-11eb-9e98-cec32e28b01f.PNG)
![lab3](https://user-images.githubusercontent.com/86701156/124007881-6f296500-d9f9-11eb-87ff-a0a5ede3c07a.PNG)

#### Invoking OpenLANE
Openlane can be invoked using docker command followed by opening an interactive session.

![lab4](https://user-images.githubusercontent.com/86701156/124007900-75b7dc80-d9f9-11eb-83d9-b8998859afb0.PNG)

 Various packages are initialized followed by preparation of the picorv32a design.
 
![lab5](https://user-images.githubusercontent.com/86701156/124008828-7dc44c00-d9fa-11eb-989e-1f699bc97572.PNG)
![lab6](https://user-images.githubusercontent.com/86701156/124009124-d7c51180-d9fa-11eb-92b1-4171ead9b2d7.PNG)

A "runs" folder is generated within the picorv32a folder.

![lab7](https://user-images.githubusercontent.com/86701156/124009377-270b4200-d9fb-11eb-957f-4f73c5baf8dc.PNG)

Since today's date is 30th June, a folder titled "30-06..." is created within the picorv32a directory:

![lab9](https://user-images.githubusercontent.com/86701156/124009563-63d73900-d9fb-11eb-8f37-fcdd43f46092.PNG)

The merger file is created during the merging operation in the pircorv32a design preparation (it merges lef and techlef files)

![lab10](https://user-images.githubusercontent.com/86701156/124009626-75204580-d9fb-11eb-945f-48b1510d45f4.PNG)

Merged.lef looks something like this:

![lab11](https://user-images.githubusercontent.com/86701156/124009634-781b3600-d9fb-11eb-91ce-053c814592d0.PNG)

Next, we run the synthesis of picorv32a design by using the *run_synthesis* command in the openlane interactive terminal:

![lab14](https://user-images.githubusercontent.com/86701156/124010076-fd064f80-d9fb-11eb-87a1-d66b99de9cd2.PNG)

The yosys and ABC tools are utilised to convert RTL to gate level netlist

![lab15](https://user-images.githubusercontent.com/86701156/124010081-fed01300-d9fb-11eb-844e-7056cbadf592.PNG)

**Calcuation of Flop Ratio:**
Flop ratio equals the Number of D Flip flops divided by Total Number of cells. 

![lab16](https://user-images.githubusercontent.com/86701156/124060928-9c9efe80-da4b-11eb-9b4a-353390683bfa.PNG) ![lab17](https://user-images.githubusercontent.com/86701156/124060933-9f99ef00-da4b-11eb-887f-ddd54e269afa.PNG)

dfxtp_4 ~ 1613,
Number of cells ~ 18036,
Therefore, Flop ratio ~ 1613/18036 ~ 0.8943

*Note: The OpenLANE github repository can be accessed [here](https://github.com/The-OpenROAD-Project/OpenLane)*

#### Characterization of synthesis results
We may check the success of the synthesis step by checking the synthesis folder for the synthesised netlist file (.v file)
![lab18](https://user-images.githubusercontent.com/86701156/124061491-8e051700-da4c-11eb-9212-d26b4ca25595.PNG)

The synthesis statistics report can be accessed within the reports directory. It is usually the last yosys file since files are listed chronologically by date of modification

![lab19](https://user-images.githubusercontent.com/86701156/124061967-7da16c00-da4d-11eb-8bf0-bf18b11e612c.PNG)![lab20](https://user-images.githubusercontent.com/86701156/124062667-ba219780-da4e-11eb-938e-88fc3e2997cb.PNG)









