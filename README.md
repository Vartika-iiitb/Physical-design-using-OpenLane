# Advanced Physical-design-using-OpenLane


#  Day 1 : Inception of open-source EDA ,OpenLANE and sky130 pdk

<details>
  <summary>
      How to talk to computers
  </summary>
  
  The QFN-48 package is a type of surface-mount integrated circuit (IC) package that is used in various electronic devices, including some Arduino-compatible microcontrollers and other components. "QFN" stands for "Quad Flat No-Lead," which describes the package's physical characteristics. Here's what some of these terms mean:

 **1. Quad:** The package has four sides or corners, typically with a lead or pad on each corner.

 **2. Flat:** The package has a flat bottom, which makes it suitable for surface-mount soldering onto a printed circuit board (PCB).

 **3. No-Lead:** Unlike traditional dual in-line packages (DIP) or surface-mount packages with visible leads or pins, QFN packages have no visible external leads or pins. Instead, they have small metal pads on the bottom of the package.

**4. 48:** The "48" in QFN-48 refers to the total number of pads or leads on the package. These pads are used for electrical connections between the IC and the PCB.

Arduino is an open-source electronics platform that uses a variety of microcontrollers. The choice of IC package depends on the specific microcontroller used on the Arduino board or module. Some Arduino-compatible boards may use microcontrollers in QFN-48 packages, among other package types.

The following figure shows the internal structure of the chip.

![Screenshot from 2023-09-16 18-23-07](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/c7944e6a-764d-4a44-8cf2-ed59244fe561)

Inside a chip, you can find various components and structures, including:

**1. Pads:** Pads are the external connections on a chip. They are the interface between the chip and the external world. Pads can include input and output pins for connecting to other electronic components or devices, power supply pins for providing voltage to the chip, and ground pins for electrical reference.

**2. Core:** The core of a chip typically refers to the central processing unit (CPU) or the primary computational engine. In the context of microprocessors or microcontrollers, the core contains the arithmetic logic unit (ALU), control unit, and registers responsible for executing instructions and performing computations.

**3.  Die:** The term "die" refers to the individual silicon chip that is fabricated on a semiconductor wafer during the manufacturing process. A semiconductor wafer typically contains multiple identical dies, each of which can be cut out and packaged as a separate integrated circuit.

**4. RISC-V SoC:** A RISC-V System-on-Chip (SoC) is an integrated circuit that incorporates the RISC-V instruction set architecture (ISA) as its CPU core. RISC-V is an open-source and customizable ISA, and RISC-V SoCs are designed to meet specific application requirements, often including CPU cores, memory, peripherals, and I/O interfaces, all on a single chip.

**5. PLL (Phase-Locked Loop):** A PLL is a circuit within a chip that generates stable and precisely controlled clock signals. PLLs are crucial for synchronizing various components of a chip, ensuring that they operate at the correct frequencies and phases.

**6. DAC (Digital-to-Analog Converter):** A DAC is a circuit within a chip that converts digital signals (binary data) into analog voltages or currents. DACs are commonly used in audio applications, communication systems, and many other contexts where analog signals are required.

These components work together to enable the chip to perform its intended functions. The specific components and their configurations can vary significantly depending on the type and purpose of the chip. For example, a microcontroller chip may have a CPU core, memory, I/O ports, and analog-to-digital converters (ADCs) in addition to the components mentioned above, while a custom ASIC (Application-Specific Integrated Circuit) might have a completely different set of components tailored to a specific task or application.

**Introduction to RisC-V**

RISC-V (pronounced "risk-five") is an open-source instruction set architecture (ISA) for designing and building computer processors and related hardware components. It's named after the "Reduced Instruction Set Computing" (RISC) philosophy, which aims to simplify processor designs by using a smaller set of instructions that execute quickly and efficiently.

![Screenshot from 2023-09-16 18-36-36](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/efe64a42-2531-4f17-86d4-cc9c5940bfa0)

**From Software Applications to Hardware**
  
In the realm of software applications, tasks are executed by the central processing unit (CPU) of a computer or device. Software programs provide instructions for the CPU to follow, and the CPU performs calculations, data processing, and various other operations based on these instructions. While software is flexible and can be updated easily, it may not always provide the highest level of performance or efficiency, especially for demanding or specialized tasks.

The benefits of this transition from software to hardware include faster execution of tasks, lower power consumption, and the ability to handle specialized workloads with greater efficiency. However, it also means that the functionality is fixed and less adaptable compared to software, which can be updated or changed more easily.

The Figure shown below shows the representation :

![Screenshot from 2023-09-16 18-40-16](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/e4bc8336-ee32-4fff-b742-5c0a56dcbcf3)
</details>
<details>
  <summary>
SoC Design and OpenLANE
  </summary>
  
System-on-Chip (SoC) design is the process of creating integrated circuits that incorporate multiple electronic components, including microprocessors, memory, input/output interfaces, and more, all on a single chip. SoCs are used in a wide range of electronic devices, from smartphones and tablets to embedded systems and IoT devices.

OpenLANE is an open-source framework for designing digital ASICs (Application-Specific Integrated Circuits). It is a complete RTL (Register-Transfer Level) to GDSII (Graphic Data System II) flow for designing ASICs using open-source tools and libraries. Here's how OpenLANE relates to SoC design:
Design Flow: OpenLANE provides a comprehensive design flow for creating ASICs, which can include components like CPU cores, memory blocks, and various other digital circuits. The design flow covers the entire process, from specifying the chip's architecture in RTL code (usually written in hardware description languages like Verilog or VHDL) to producing the final GDSII layout for fabrication.

**1. Open Source:** One of the key features of OpenLANE is its open-source nature. This means that the entire design flow, including synthesis, placement, routing, and physical design steps, can be performed using freely available and community-supported tools and libraries. This openness reduces the barriers to entry for ASIC design and promotes collaboration within the hardware design community.

**2. Automated and Scriptable:** OpenLANE incorporates a wide range of automation and scripting capabilities. It can automate many of the tedious and error-prone tasks involved in ASIC design, such as synthesis, place and route, and optimization. Users can customize and script the flow to suit their specific requirements.

**3. Standard Cells and Libraries:** OpenLANE leverages standard cell libraries, which are collections of pre-designed and characterized digital logic cells (like AND gates, flip-flops, etc.) that are readily available for use in ASIC design. It also supports standard cell libraries from various foundries, allowing designers to target different fabrication technologies.

**4. OpenROAD Integration:** OpenLANE is part of the OpenROAD project, which aims to develop an open-source and automated RTL-to-GDSII digital ASIC design flow. OpenROAD includes tools for optimization, placement, and routing, and OpenLANE utilizes these tools to streamline the design process further.

**5. Community and Collaboration:** The open-source nature of OpenLANE encourages collaboration among hardware designers, researchers, and engineers. It has a growing user community, and contributions from various individuals and organizations are welcomed.

In summary, OpenLANE is a powerful open-source tool that simplifies the process of designing ASICs, including SoCs. It provides a complete and automated design flow, making it accessible to a broader range of users and promoting innovation in digital hardware design. This tool has the potential to accelerate the development of custom SoCs and other digital ASICs for a variety of applications.

![Screenshot from 2023-09-16 19-05-11](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/3f4ede54-22ba-486b-a214-e573dd3dfdd8)

**1 RTL IP's(Register Transfer Level Intellectual Property)**
RTL IPs, or Register-Transfer Level Intellectual Properties, are pre-designed and pre-verified building blocks or functional modules for use in digital integrated circuit (IC) design. These IPs are created at the register-transfer level (RTL), which is a level of abstraction in hardware description languages like Verilog and VHDL that represents the behavior of a digital circuit in terms of registers and data transfers between them. RTL IPs are used to accelerate the design and development of complex digital systems and integrated circuits. RTL IPs significantly reduce development time and effort by providing verified and reusable building blocks for digital IC design. They are widely used in various industries, including consumer electronics, telecommunications, automotive, and industrial automation, to accelerate the design of complex digital systems and reduce time-to-market.

**2. EDA TOOLS**
EDA (Electronic Design Automation) tools are a category of software applications and tools used by electrical engineers and integrated circuit (IC) designers to design, simulate, verify, and analyze electronic systems and integrated circuits. These tools play a crucial role in the development and optimization of electronic hardware, ranging from individual components to complex systems. EDA tools are used in various stages of the design process, from concept to fabrication. EDA tools are indispensable in modern electronics design, as they streamline the design process, reduce design iterations, and help ensure the reliability and performance of electronic systems and integrated circuits. The choice of EDA tools depends on the specific requirements of the design project and the target application.

**3. PDK**
PDK stands for "Process Design Kit." It is a critical component in the development of integrated circuits (ICs) and refers to a collection of files, data, and models provided by a semiconductor foundry or manufacturing facility. The PDK serves as a bridge between the design tools and the foundry's fabrication process, enabling chip designers to create layouts and simulations that are compatible with the manufacturing process.

Here are the key components and functions of a Process Design Kit (PDK) in VLSI design:

**1.Technology Data:** The PDK includes detailed information about the foundry's manufacturing process, such as the specific fabrication steps, the materials used, and the electrical characteristics of the transistors and interconnects. This data is essential for designing circuits that will function correctly when fabricated.

**2. Design Rules:** Design rules are a set of constraints and guidelines that dictate how various elements of the chip (e.g., transistors, interconnects, and other structures) should be placed and sized to ensure manufacturability. The PDK provides design rule documents and data to help designers adhere to these constraints.

**3. Device Models:** PDKs include models for various electronic devices, such as transistors, diodes, and capacitors. These models describe how these devices behave electrically under different conditions, allowing designers to simulate and analyze the performance of their circuits accurately.

**4. Library Cells:** The PDK includes a library of standard cells, which are pre-designed building blocks commonly used in chip design. These cells include logic gates, flip-flops, multiplexers, and other components. Designers can use these cells to create their custom digital circuits.

The figure shown below depicts the flow:

![Screenshot from 2023-09-16 19-05-17](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/698b6b22-612a-4e4c-b6d3-15c03b3a593b)


**Simplified RTL2GDS Flow**
The RTL2GDS (Register-Transfer Level to Graphic Data System) flow is a series of steps and processes involved in the design and manufacturing of integrated circuits (ICs). This flow takes a digital design described at the RTL (Register-Transfer Level) and transforms it into a physical layout that can be fabricated as an actual chip. Here are the key steps and components of the RTL2GDS flow:

**1. RTL Design:** The RTL design phase involves creating a high-level description of the digital circuit using hardware description languages (HDLs) like Verilog or VHDL. This description captures the functional behavior of the circuit, including the relationships between registers and data transfers.

**2. Synthesis:** In the synthesis step, the RTL code is transformed into a gate-level representation. Logic synthesis tools take the RTL description and map it to standard cells from a library (PDK, or Process Design Kit) provided by the semiconductor foundry. The output is a netlist that specifies how standard cells are interconnected.

**3. Floor Planning:** Floor planning involves determining the physical placement of various functional blocks within the chip. It considers factors like the size and aspect ratio of the chip, the location of the input/output (I/O) pads, and the placement of major components.

**4. Placement:** Placement tools take the synthesized netlist and assign specific locations for each standard cell on the chip. The goal is to optimize for factors like area, power, and signal delay.

**5. Clock Tree Synthesis (CTS):** CTS tools create a clock distribution network that ensures all flip-flops and registers receive a stable and synchronized clock signal. Clock skew (variation in clock arrival times) is minimized to maintain timing integrity.

**6. Routing:** The routing step involves determining how to connect the various components and standard cells while adhering to design rules and constraints. This process creates the physical wires (metal layers) that carry signals between different parts of the chip.

**7. Design for Manufacturing (DFM):** DFM techniques are employed to ensure that the chip design is manufacturable. This includes checks for lithography issues, density violations, and other manufacturing-related concerns.

**8. Static Timing Analysis (STA):** STA tools analyze the timing of the chip's paths to ensure that they meet the required performance specifications. Timing violations are flagged and resolved during this phase.

**9. Physical Verification:** Physical verification tools perform checks to ensure that the chip layout complies with design rules and specifications. This includes checks for design rule violations, antenna effects, and other physical issues.

**10. GDSII Generation:** GDSII is a standard file format used to represent the final chip layout in a graphical form. GDSII files are generated from the layout data.

**11. Tapeout:** The final GDSII files are submitted to the semiconductor foundry for fabrication. This step involves preparing the data for photolithography and the manufacturing process.

**12. Mask Generation:** The foundry uses the GDSII data to create photomasks, which are used to pattern the chip's layers during the semiconductor manufacturing process.

**13. Manufacturing:** The semiconductor fabrication process involves multiple steps, including photolithography, etching, implantation, and more, to create the physical silicon wafer with the desired integrated circuits.

**14. Packaging and Testing:** Once the wafers are manufactured, they are diced into individual chips, packaged, and tested to ensure functionality and quality.

The RTL2GDS flow is a complex and highly specialized process that requires expertise in digital design, semiconductor physics, and manufacturing. It is a critical part of bringing digital designs to life as physical integrated circuits used in various electronic devices and systems.

![Screenshot from 2023-09-17 02-20-53](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/b16c3eda-7a5b-47e8-8127-478a143f9ba0)

</details>

<details>
  <summary>
    OpenLANE detailed ASIC design flow
  </summary>
  
OpenLane is an open-source RTL-to-GDSII (Register-Transfer Level to Graphic Data System) flow, which is a complete toolchain for designing and manufacturing integrated circuits. OpenLane automates many of the steps involved in ASIC (Application-Specific Integrated Circuit) design, such as synthesis, placement, routing, and physical verification. It's part of the broader open-source hardware movement and is designed to make ASIC design more accessible and affordable.
  On the other hand, Strive chipsets are a family of RISC-V System on Chips (SoCs) designed using the SkyWater 130nm process. RISC-V is an open standard instruction set architecture (ISA) based on established reduced instruction set computer (RISC) principles.


  striVe SoC family:
  
  ![Screenshot from 2023-09-17 02-40-28](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/221b6c67-4454-4fcb-bdf7-5ae595b0b19f)

OpenLANE ASIC Flow:

1. RTL Synthesis, Technology Mapping, and Formal Verification:
Tools: Yosys (for RTL synthesis), ABC (for technology mapping and formal verification).

Static Timing Analysis:
Tool: OpenSTA (for static timing analysis).

Floor Planning:
Tools: init_fp (initial floorplanning), ioPlacer (I/O placement), pdn (power distribution network planning), tapcell (tap cell insertion).

Placement:
Tools: RePLace (global placement), Resizer (optional for resizing cells), OpenPhySyn (formerly used for placement), OpenDP (detailed placement).

Clock Tree Synthesis:
Tool: TritonCTS (for clock tree synthesis).

Fill Insertion:
Tools: OpenDP (for filler placement).

Routing:
Global Routing: FastRoute or CU-GR (formerly used).
Detailed Routing: TritonRoute (for detailed routing) or DR-CU (formerly used).

SPEF Extraction:
Tools: OpenRCX (or SPEF-Extractor, formerly used) for Standard Parasitic Exchange Format (SPEF) extraction.

GDSII Streaming Out:
Tools: Magic and KLayout (for viewing and editing GDSII files).

Design Rule Checking (DRC) Checks:
Tools: Magic and KLayout (for DRC checks).

Layout vs. Schematic (LVS) Check:
Tool: Netgen (for LVS checks).

Antenna Checks:
Tool: Magic (for antenna checks).

Circuit Validity Checker:
Tool: CVC (for circuit validity checking).

These open-source tools, when used collectively, provide a complete and automated ASIC design and verification flow through OpenLane.

The fig shown below depicts the OpenLANE ASIC Flow:

![Screenshot from 2023-09-17 02-51-28](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/6edc6730-1a1c-4ebd-8ef9-942f6d899c2c)

</details>
<details>
  <summary>
    OpenLANE Installation
  </summary>
  
**Steps to Install OpenLANE**

  ```
  cd $HOME
sudo apt-get update
sudo apt-get upgrade
sudo apt install -y build-essential python3 python3-venv python3-pip make git

```
Invoking OpenLANE
```


cd ~/OpenLane
make mount
./flow.tcl -interactive
package require openlane 0.9
prep -design picorv32a
run_synthesis

```

Steps to install docker:

```
sudo apt-get remove docker docker-engine docker.io containerd runc
# Installation of requirements
sudo apt-get update
sudo apt-get install \
   ca-certificates \
   curl \
   gnupg \
   lsb-release
# Add the keyrings of docker
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
# Add the package repository
echo \
   "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
# Update the package repository
sudo apt-get update

# Install Docker
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin

# Check for installation
sudo docker run hello-world

```

Fig below shows the installation:

![Screenshot from 2023-09-17 11-44-41](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/8dbe291f-7c57-4d8d-b984-b4cebaa73def)

For run synthesis:
![Screenshot from 2023-09-17 11-47-07](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/cb22d155-1f26-4e7b-9cb5-0b8d70d469d8)

</details>

# Day2: Good Floorplan vs Bad Floor Plan and Introduction to library cells
<details>
  <summary>
    Chip Floorplanning and considerations
  </summary>
  
   **Core**
   The width of the core typically refers to the physical size or dimensions of the central processing unit (CPU) or processor core within a microchip. It is usually measured in nanometers (nm) or micrometers (µm). For example, you might hear about a "14nm core" or a "7nm core," indicating the feature size of the core's transistors.
The height of the core is not commonly referred to in the same way as the width. Instead, the core's size is usually described in terms of its area, which is determined by multiplying its width and height.

**Die**
The width of the die is typically the physical measurement of the semiconductor wafer after all the individual ICs (integrated circuits) have been fabricated on it but before they are cut apart. Die widths can vary significantly depending on the specific manufacturing process and the design of the chips being produced. They can range from a few millimeters to several centimeters or more.

Similar to the core, the height of the die is not a common parameter of discussion. Instead, the die's size is often described in terms of its area, which is the product of its width and height.

The fig shown below shows the representation:

![Screenshot from 2023-09-17 13-02-05](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/8d6550e2-42b0-4a7c-bc3e-2a174ba60046)

  **Utilization Factor**
  
  In the context of ASIC (Application-Specific Integrated Circuit) design, the term "utilization factor" refers to the ratio of the occupied area of the chip to the total available silicon area on the semiconductor wafer. It is often expressed as a percentage. The utilization factor provides insight into how efficiently the chip's resources, including logic gates, memory cells, and other components, are used within the available silicon real estate.

Here's how to calculate the utilization factor:

Utilization Factor (%) = (Occupied Silicon Area / Total Silicon Area) x 100

Fig below shows the utilization Factor:

![Screenshot from 2023-09-17 12-55-02](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/070e4c6f-1a28-4249-b3ce-e42b5317a3e4)



**Aspect ratio**
 Aspect ratio will decide the size and shape of the chip. It is the ratio between horizontal routing resources to vertical routing resources (or) ratio of height and width. Aspect ratio = width/height.Aspect ratio of 1 signifies that the die is of square shape and any other value other than 1 signifies that the die is rectangular shape.

 **Preplaced cells**
 Preplaced cells, often referred to as "macrocells" or "hard macros," are fixed or predefined blocks of logic or functional units within the layout of an integrated circuit (IC) or an ASIC (Application-Specific Integrated Circuit). Unlike standard cells, which are synthesized and placed automatically during the design process, preplaced cells are manually positioned and sized by the chip designer. These cells are typically used for specific, well-defined functions and are placed in critical areas of the chip layout to meet certain design objectives.Pre-placed cells are often used for critical components of a design, such as memory blocks, analog modules, or specialized digital circuits that need to be precisely located to meet performance, power, or area constraints. Placing them manually ensures that they are in the optimal positions for meeting these requirements.In large and complex chip designs, pre-placed cells can be used to create a hierarchical structure, where certain functional blocks or subsystems are pre-placed and interconnected. This approach simplifies the overall design process and allows for better management of the design's complexity.

![Screenshot from 2023-09-17 14-31-18](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/56defa42-ed58-486a-ab7b-0eefb33bebe4)

**Decoupling Capacitor**

![Screenshot from 2023-09-17 14-33-36](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/5484fa44-8024-41bf-bd4f-38fb1fce0dfb)

**Noise Margin**

![Screenshot from 2023-09-17 14-36-06](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/7cd9658c-2095-4d76-b8b7-373c8e1d46a9)

Noise margin, in the context of ASIC (Application-Specific Integrated Circuit) design, refers to the amount of noise or voltage fluctuations that a digital logic gate or circuit can tolerate while still correctly recognizing logic levels (0 or 1). It is an essential consideration in the design of digital circuits to ensure reliable operation in real-world conditions where noise and variations in supply voltage can occur. Noise margin is typically expressed in volts and can be categorized into two main types: high noise margin (NMH) and low noise margin (NML).

High Noise Margin (NMH): NMH is the maximum voltage noise that can be added to the HIGH (logic 1) level of a digital signal without causing the gate to misinterpret it as a LOW (logic 0) level. In other words, it represents the tolerance of the gate to noise on the high side.

NMH = VOH - VIH

VOH: The minimum output voltage for a logic HIGH.
VIH: The minimum input voltage that the gate recognizes as a logic HIGH.
Low Noise Margin (NML): NML is the maximum voltage noise that can be added to the LOW (logic 0) level of a digital signal without causing the gate to misinterpret it as a HIGH (logic 1) level. It represents the tolerance of the gate to noise on the low side.

NML = VIL - VOL

VIL: The maximum input voltage that the gate recognizes as a logic LOW.
VOL: The maximum output voltage for a logic LOW.
The difference between NMH and NML indicates the margin of safety against noise in a digital circuit. A larger noise margin provides better immunity to noise and ensures more reliable operation. Designers typically aim to maximize both NMH and NML to create robust digital circuits.

Noise margin is influenced by various factors, including:

Threshold voltage (VTH) of the transistors used in the logic gates.
Supply voltage (VDD) and ground voltage (GND) levels.
Variation in environmental conditions, such as temperature and voltage fluctuations.
Process variations during chip manufacturing.
To ensure proper noise margin in ASIC design, designers must consider these factors and select appropriate transistor sizes, supply voltage levels, and design techniques. Additionally, performing noise margin analysis and simulation during the design phase helps identify potential issues and allows for adjustments to improve circuit robustness in noisy environments.

In summary, noise margin in ASIC design quantifies the tolerance of digital logic gates to noise and voltage fluctuations. High noise margin ensures reliable operation and immunity to noise-induced errors in digital circuits.

**Power Planning**
Power planning, in the context of integrated circuit (IC) design, is a critical step in the process of ensuring that the chip operates reliably while managing power consumption efficiently. It involves the strategic distribution and management of power supply networks, as well as the control of power domains and voltage levels within the chip. The primary goals of power planning are to provide stable power delivery to all components, minimize power dissipation, and avoid voltage drop issues.

**Pin Placement**
Pin placement, in the context of integrated circuit (IC) design, refers to the strategic placement of input and output (I/O) pins or pads on the chip's physical layout. This process is crucial for ensuring proper connectivity between the chip and external devices, such as other chips, connectors, or printed circuit boards (PCBs). Effective pin placement is essential for achieving electrical, mechanical, and manufacturing objectives in IC design.

**Floorplan using OpenLANE**

```
run_floorplan
```

![Screenshot from 2023-09-17 11-48-26](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/7ad02b3e-5d06-45c7-97a9-34b4fddda932)

Magic is invoked after moving to the floorplan directory:

```
magic  /home/vartika/.volare/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.min.lef def read picorv32.def

```
Below is the representation:

![Screenshot from 2023-09-17 11-48-26](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/6742936d-a721-4ebf-a6f4-f0e5d6030d0e)

**Initial Place Design**

**Library Binding and placement**

Netlist binding and Initial Placement

1. All the logic cells in the netlist are visualised as physical cells with a defined width and height for design
2. A library has all the physical cells with each logic functionality with timing and area information.
3. Library also has different physical variants of logic cells
4. The logic cells of the generated netlist should not be placed over the pre-placed cells.

**Optimized placement**

1. Logic cells are placed such that they are close to their respective inputs on the die.
2. Optimized placement is done by placing, input flop close to the input port and output close to the output port.
3. We estimate the wire length and capacitance and based on that we insert repeaters, if there is a long path from the input port to the flipflop
4. Slew is dependent on the capacitance value, higher is the capacitance more is the slew.
5. If the distance between the input port and flip-flop is not sufficient to maintain the signal integrity, we add buffers/repeaters in the path to reproduce 
   input signal through the path without any loss of signal.
6. The cells which work at very high frequency are made sure to be placed together, so that there is no delay produced from the wires between the logic cells.

   **Optimized cell and routed cell**
   
   ![Screenshot from 2023-09-17 14-52-24](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/b491695f-d550-476d-9397-ac1aec7e5087)

**Placement**
Placement in openlane occurs in two stages:

1. Global Placement: It finds optimal position for all cells which may not be legal and cells may overlap. Optimization is done through reduction of half parameter wire length[HPWL]. Overlap parameter should also reduce while we run placement.
2. Detailed Placement: It alters the position of cells placed in the global placement step to legalise them
use :

```
  run_placement
```
To view Placement:

```
  cd ~/OpenLane/designs/picorv32a/runs/RUN_2023.09.14_10.50.04/results/placement
  magic -T /home/vartika/.volare/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.nom.lef def read picorv32.def &
```

![Screenshot from 2023-09-17 11-53-09](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/9e1328e4-06ae-416c-91df-856a0c5c1c2e)


![Screenshot from 2023-09-17 11-55-14](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/ea6cbdbf-4b37-4235-b877-bf224d8d3122)

![Screenshot from 2023-09-17 11-56-30](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/7c77732a-8eb9-44be-90d5-09c8be776210)

**Cell Design Flow**

The cell design flow in ASIC (Application-Specific Integrated Circuit) design refers to the process of designing and creating standard cells, which are the fundamental building blocks of digital integrated circuits. Standard cells are pre-designed, reusable modules that include basic logic gates, flip-flops, latches, and other components. They play a crucial role in digital IC design, allowing designers to create complex digital circuits efficiently. The cell design flow typically involves the following steps:

1. Specification and Requirements:

1.1 Define the functional requirements for the standard cell library.
1.2 Determine the target technology node, voltage levels, and other design parameters.
1.3 Specify the library's logical and electrical characteristics, including cell types, drive strengths, and functionality.

2. Cell Architecture and Cell Library Definition:

2.1 Define the architecture of the standard cells, including the height and width of each cell, the number of input and output pins, and the arrangement of internal transistors.
2.2 Create a library of cell templates with different functionalities and drive strengths, ranging from basic gates to more complex functions.
Schematic Design:

3. Create schematic diagrams for each standard cell in the library.
3.1Design and layout the internal logic gates, interconnections, and transistors to implement the desired functionality.
3.2 Ensure that the cells adhere to the specified logical and electrical characteristics.
   
4. Simulation and Verification:
4.1 Simulate the standard cell designs using electronic design automation (EDA) tools and digital simulators.
4.2 Verify that the cells meet timing constraints, operate correctly, and adhere to logical and electrical specifications.
4.3 Perform static timing analysis (STA) to assess the cell's performance under various conditions.
   
5. Layout Design:
   
5.1 Generate the physical layout of each standard cell, considering the placement and sizing of transistors, routing of metal layers, and adherence to design rules.
5.2 Follow foundry-specific design rules and guidelines to ensure manufacturability.
5.3 Implement DFM (Design for Manufacturability) techniques to improve the manufacturability of the cells.

6. Extraction and Modeling:

6.1 Extract parasitic capacitance and resistance information from the layout.
6.2 Create models (e.g., timing, power, and noise models) for the standard cells based on the extracted data.

7. Characterization:

7.1 Characterize the standard cells by measuring their electrical characteristics, such as timing, power consumption, and noise sensitivity.
7.2 Generate libraries of timing models for use in digital synthesis and static timing analysis.

8. Quality Assurance and Testing:

8.1 Perform extensive testing and verification to ensure that the standard cells meet the specified requirements and adhere to design and manufacturing rules.
8.2 Address any issues, optimize cell designs, and update the library as needed.

9. Documentation:

9.1 Create comprehensive documentation for each standard cell, including datasheets, functional descriptions, and usage guidelines.
9.2 Document the library's logical and electrical characteristics for designers' reference.

10. Integration into the Design Flow:

10.1 Integrate the standard cell library into the broader ASIC design flow, making it available for digital design and synthesis tools.
10.2 Ensure that the library is compatible with industry-standard EDA tools and design methodologies.
10.3 The cell design flow is a fundamental part of ASIC design, providing designers with a library of well-characterized and verified building blocks that can be used to construct complex digital circuits efficiently. The quality and performance of the standard cell library have a significant impact on the overall success of an ASIC design project.

The fig shown below shows the Cell design flow:

![Screenshot from 2023-09-17 15-01-40](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/c3fb1380-1c61-48af-9b5f-77f1308009f8)

![Screenshot from 2023-09-17 15-08-42](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/45bbde36-71a6-4019-b18a-a26153e3fdae)

![Screenshot from 2023-09-17 15-08-47](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/0401b3c4-7a8d-409a-a9d2-c5545da5735b)

![Screenshot from 2023-09-17 15-09-03](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/7179f8b0-23d7-4614-a36c-5f5443668c38)

The stick diagram for the following is shown below:

![Screenshot from 2023-09-17 15-10-41](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/244a22ef-143d-4eeb-af6b-7f6768b586d4)

</details>

<details>
  <summary>
    Cell Design and characterisation flow
  </summary>
  All the standard cells used in the design are placed in a library. We get a variant of standard cells in terms of functionality, area and power.
Each cell goes through cell design flow before being used in our design.

  **Characterisation Flow**
  Characterization in VLSI refers to the process of analyzing and documenting the electrical behavior of electronic components, such as transistors, logic gates, memory cells, and standard cells, under various operating conditions. Characterization is essential for accurate circuit simulation and helps ensure that integrated circuits (ICs) meet their performance, power, and timing requirements.
1. Read in the model files
2. Read the extracted spice netlist
3. Recognize behaviour of the model
4. Read the sub-circuits of inverter
5. Attach necessary power source (Vdd, GND)
6. Apply the stimulus
7. Provide necessary output capacitance
8. Provide simulation command

   ![Screenshot from 2023-09-17 15-19-51](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/337d10d7-f7df-496e-a5c6-56c97f86d5b9)

The following fig shown below shows the Characterization Flow:

![Screenshot from 2023-09-17 15-16-44](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/80925a34-10f5-4793-a001-0fd0741b57fb)

![Screenshot from 2023-09-17 15-16-52](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/ecdde2cf-84ef-446a-ab32-826b754b59cc)

</details>
<details>
  <summary>
    Timing Characterization Parameter
  </summary>
  The Timing Threshold Definitions:
  
  ![Screenshot from 2023-09-17 15-23-16](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/28c1a1e0-0229-41ef-9ca7-ddda17fe0ae2)

**Propagation Delay**
 The time difference between when the transitional input reaches 50% of its final value and when the output reaches 50% of its final value.

![Screenshot from 2023-09-17 15-23-27](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/8c644640-6cc7-4203-bc1b-4627b37f9924)

**Transition Time**
 Transition time is known as time needed to a signal to rise from 10% to 90% or to fall from 90% to 10%. The former is called rise time and later is known as fall time.

![Screenshot from 2023-09-17 15-23-41](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/2ff3ea82-53ed-4f33-bffe-b12bbef8951f)

```
rise delay =  time(out_fall_thr) - time(in_rise_thr)

Propagation delay = time(out_thr) - time(in_thr)

Fall transition time: time(slew_high_fall_thr) - time(slew_low_fall_thr)

Rise transition time: time(slew_high_rise_thr) - time(slew_low_rise_thr)
```

</details>
