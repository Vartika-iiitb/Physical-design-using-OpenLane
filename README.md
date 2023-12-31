# Advanced Physical-design-using-OpenLane


#  DAY 1 : Inception of open-source EDA ,OpenLANE and sky130 pdk

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

# DAY 2: Good Floorplan vs Bad Floor Plan and Introduction to library cells
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

# DAY 3 : Design Library cell using Magic Layout and ngspice Characterization 

<details>
  <summary>
    Labs for CMOS inverter for ngspice simulations
  </summary>
  
  **Inverter**
  A CMOS inverter, short for Complementary Metal-Oxide-Semiconductor inverter, is a fundamental digital electronic circuit that performs the basic logical operation of inversion. In other words, it takes an input signal and produces an output signal that is the logical complement of the input. If the input is high (logic 1), the output will be low (logic 0), and vice versa.

The input signal is applied to the gate terminals of both the NMOS and PMOS transistors. The output is taken from the connection point (the drain of NMOS and the source of PMOS) between these two transistors.

NMOS Operation: When the input is logic high (1), the NMOS transistor turns on because a positive voltage is applied to its gate. This establishes a low-resistance path between the output and ground, causing the output to be pulled to logic low (0).

PMOS Operation: Conversely, when the input is logic low (0), the PMOS transistor turns on because a low voltage is applied to its gate. This establishes a low-resistance path between the output and the power supply voltage (VDD), causing the output to be pulled to logic high (1).

The following fig shows the CMOS Inverter with it's respective nodes:

![Screenshot from 2023-09-17 15-35-16](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/d891cb52-592e-45b3-974b-22c80dc0b30c)

The following fig shows the spicedeck Simulation:

![Screenshot from 2023-09-17 15-36-23](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/735f1fb9-3d19-4ca2-9421-ba9f3d1b29de)



</details>
<details>
  <summary>
    Inception of layout A CMOS fabrication Process
  </summary>
  
  **The output of 16 mask CMOS process**
  
  ![Screenshot from 2023-09-17 22-22-55](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/d2dbc504-4ca0-4303-9127-3978b153dde8)

 **Basic layers layout and LEF using inverter**
 
1. We see the layers which are required for CMOS inverter from the layout.
2. Gates of both PMOS and NMOS are connected together and fed to input, NMOS source connected to ground(here, VGND), PMOS source is connected to VDD(here, VPWR)
3. Drains of PMOS and NMOS are connected together and fed to output(here, Y).
4. The First layer in skywater130 is localinterconnect layer(locali) , above that metal 1 is purple color and metal 2 is pink color.

</details>

<details>
  <summary>
    sky130 tech file labs
  </summary>
  The model file for the same is shown below:

```
* SPICE 3f5 Level 8, Star-HSPICE Level 49, UTMOST Level 8

.lib cmos_models 
* DATE: Feb 23/01
* LOT: T0BM                  WAF: 07
* Temperature_parameters=Default
.MODEL nmos  NMOS (                                LEVEL   = 49
+VERSION = 3.1            TNOM    = 27             TOX     = 5.8E-9
+XJ      = 1E-7           NCH     = 2.3549E17      VTH0    = 0.3907535
+K1      = 0.4376003      K2      = 8.265151E-3    K3      = 4.214601E-3
+K3B     = -3.7220937     W0      = 2.517345E-6    NLX     = 2.310668E-7
+DVT0W   = 0              DVT1W   = 0              DVT2W   = 0
+DVT0    = 0.2411602      DVT1    = 0.3707226      DVT2    = -0.5
+U0      = 316.5922683    UA      = -9.89493E-10   UB      = 2.154013E-18
+UC      = 2.474632E-11   VSAT    = 1.254499E5     A0      = 1.2735648
+AGS     = 0.2428704      B0      = 2.579719E-8    B1      = -1E-7
+KETA    = 4.87168E-4     A1      = 0              A2      = 0.5196633
+RDSW    = 120            PRWG    = 0.5            PRWB    = -0.2
+WR      = 1              WINT    = 2.357855E-8    LINT    = 1.210018E-9
+DWG     = 2.292632E-9
+DWB     = -9.94921E-10   VOFF    = -0.1039771     NFACTOR = 1.3905578
+CIT     = 0              CDSC    = 2.4E-4         CDSCD   = 0
+CDSCB   = 0              ETA0    = 3.894977E-3    ETAB    = 7.800632E-4
+DSUB    = 0.0307944      PCLM    = 1.7312397      PDIBLC1 = 0.999135
+PDIBLC2 = 4.850036E-3    PDIBLCB = -0.0866866     DROUT   = 0.8612131
+PSCBE1  = 7.995844E10    PSCBE2  = 1.457011E-8    PVAG    = 0.0099984
+DELTA   = 0.01           RSH     = 5              MOBMOD  = 1
+PRT     = 0              UTE     = -1.5           KT1     = -0.11
+KT1L    = 0              KT2     = 0.022          UA1     = 4.31E-9
+UB1     = -7.61E-18      UC1     = -5.6E-11       AT      = 3.3E4
+WL      = 0              WLN     = 1              WW      = -1.22182E-16
+WWN     = 1.2127         WWL     = 0              LL      = 0
+LLN     = 1              LW      = 0              LWN     = 1
+LWL     = 0              CAPMOD  = 2              XPART   = 0.4
+CGDO    = 3.11E-10       CGSO    = 3.11E-10       CGBO    = 1E-12
+CJ      = 1.741905E-3    PB      = 0.9876681      MJ      = 0.4679558
+CJSW    = 3.653429E-10   PBSW    = 0.99           MJSW    = 0.2943558
+CF      = 0              PVTH0   = -0.01          PRDSW   = 0
+PK2     = 2.589681E-3    WKETA   = -1.866069E-3   LKETA   = -0.0166961      )
*
.MODEL pmos  PMOS (                                LEVEL   = 49
+VERSION = 3.1            TNOM    = 27             TOX     = 5.8E-9
+XJ      = 1E-7           NCH     = 4.1589E17      VTH0    = -0.583228
+K1      = 0.5999865      K2      = 6.150203E-3    K3      = 0
+K3B     = 3.6314079      W0      = 1E-6           NLX     = 1E-9
+DVT0W   = 0              DVT1W   = 0              DVT2W   = 0
+DVT0    = 2.8749516      DVT1    = 0.7488605      DVT2    = -0.0917408
+U0      = 136.076212     UA      = 2.023988E-9    UB      = 1E-21
+UC      = -9.26638E-11   VSAT    = 2E5            A0      = 0.951197
+AGS     = 0.20963        B0      = 1.345599E-6    B1      = 5E-6
+KETA    = 0.0114727      A1      = 3.851541E-4    A2      = 0.614676
+RDSW    = 1.496983E3     PRWG    = -0.0440632     PRWB    = -0.2945454
+WR      = 1              WINT    = 7.879211E-9    LINT    = 2.894523E-8
+DWG     = -1.112097E-8
+DWB     = 9.815716E-9    VOFF    = -0.1204623     NFACTOR = 1.2259401
+CIT     = 0              CDSC    = 2.4E-4         CDSCD   = 0
+CDSCB   = 0              ETA0    = 0.3325261      ETAB    = -0.0623452
+DSUB    = 0.9206875      PCLM    = 0.833903       PDIBLC1 = 9.948506E-4
+PDIBLC2 = 0.0191187      PDIBLCB = -1E-3          DROUT   = 0.9938581
+PSCBE1  = 2.887413E10    PSCBE2  = 8.325891E-9    PVAG    = 0.8478443
+DELTA   = 0.01           RSH     = 3.6            MOBMOD  = 1
+PRT     = 0              UTE     = -1.5           KT1     = -0.11
+KT1L    = 0              KT2     = 0.022          UA1     = 4.31E-9
+UB1     = -7.61E-18      UC1     = -5.6E-11       AT      = 3.3E4
+WL      = 0              WLN     = 1              WW      = 0
+WWN     = 1              WWL     = 0              LL      = 0
+LLN     = 1              LW      = 0              LWN     = 1
+LWL     = 0              CAPMOD  = 2              XPART   = 0.4
+CGDO    = 2.68E-10       CGSO    = 2.68E-10       CGBO    = 1E-12
+CJ      = 1.864957E-3    PB      = 0.976468       MJ      = 0.4614408
+CJSW    = 3.118281E-10   PBSW    = 0.6870843      MJSW    = 0.3021929
+CF      = 0              PVTH0   = 6.397941E-3    PRDSW   = 30.410214
+PK2     = 2.100359E-3    WKETA   = 5.428923E-3    LKETA   = -0.0111599      )
*
.endl
```
Here is the cmos.cir file:

![Screenshot from 2023-09-17 19-33-20](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/9c52bb2f-c242-4ae6-bc87-58c07201ee01)

Following Command have been used to run and execute ngspice:

```
source cmos.cir
run
setplot
set the dc plot
display
plot out vs in
```

![Screenshot from 2023-09-17 19-32-58](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/37fb50ed-7fb6-465c-9314-052f083de012)

Now if we increase the width of PMOS W = 0.9375, observe the changes:

![Screenshot from 2023-09-17 19-32-58](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/822a5df2-a544-42ef-b870-f2b50f7d9f54)

Here is the cmos.cir file:

![Screenshot from 2023-09-17 19-33-20](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/b66d4e20-b1f9-4063-9efb-b631a919b47e)



![Screenshot from 2023-09-17 19-33-47](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/9aa73ddc-b7aa-4049-be07-643819c8cce7)

out vs time graph is shown below:

![Screenshot from 2023-09-17 19-45-45](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/ab1348c0-3ca1-41d5-b382-4a54fc04c942)

out vs time vs in graph is shown below:

![Screenshot from 2023-09-17 19-47-34](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/e2962353-94d6-4c89-be51-79102ad89ac4)


The zoomed in graph for the previous one is shown below:

![Screenshot from 2023-09-17 19-49-20](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/6dd307ae-a722-4e53-8643-3c8a0a327642)


First git clone the vsdstdcelldesign repository using below command :
```
git clone https://github.com/nickson-jose/vsdstdcelldesign
```
There will be sky130_inv.mag file

Use the sky130A.tech file from the libs folder when you are running the magic.

To run the layout design in magic use the below command :

```
magic -T sky130A.tech sky130_inv.mag &
```

![Screenshot from 2023-09-17 19-15-06](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/0cdaa1f0-7408-4ec0-8d9a-450b4a0d965a)

![Screenshot from 2023-09-17 19-15-53](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/20fed668-9df9-43ca-a449-dde89437f34f)

![Screenshot from 2023-09-17 22-45-37](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/1a00f0f5-352a-4aed-9ae2-610693630855)


Now to extract it to spice use below command in magic terminal :
```
ext2spice
```
It will create sky130_inv.spice file :

![Screenshot from 2023-09-17 20-11-17](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/0b7a92d7-3324-4d64-bf07-9bcc11108fc5)

Now include the pshort.lib and nshort.lib libraries and modified the models.

Then pulse is given in which format is below:

PULSE(V1 V2 Tdelay Trise Tfall Ton Tperiod Ncycles)

Below is the modified spice file:

![Screenshot from 2023-09-17 20-20-37](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/7462dbb0-91e1-4866-8114-cca0fb6fe3d5)

Executing it in ngspice:

![Screenshot from 2023-09-17 22-57-25](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/0f6e2240-438a-4f6c-aaf7-34692e7fcd4b)

</details>

# DAY 4 : Pre Layout Timing Analysis and importance of good clock Tree
<details>
  <summary>
    Timing Modelling using delay tables
  </summary>

Convert grid into Track info


  ![Screenshot from 2023-09-18 00-36-09](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/9d02bc81-8ffd-4132-ba0d-a2a93bfc292c)

 key criterion outlined in the tracks.info specification is that ports must be positioned at the juncture of both horizontal and vertical tracks. Specifically, when dealing with the CMOS Inverter, ports A and Y are designated to reside within the li1 layer. It is imperative to guarantee that these ports are indeed situated precisely at the intersection of horizontal and vertical tracks.Below is the command:

```
grid 0.46um 0.34um 0.23um 0.17um
```
The following fig shows the grid representation:

![Screenshot from 2023-09-18 00-39-30](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/c19b1d70-c880-429e-813a-0a35549317a1)

The subsequent step in the process involves the extraction of the LEF file for the completed layout of the cell. This crucial step is essential to facilitate the placement and routing tools effectively. It necessitates the precise specification of characteristics and definitions for the cell's pins. Ports, which represent the declared PINs of the macro, are encapsulated within a cell and are formatted as a macro cell in LEF files. Our primary objective is to generate an LEF file in a predefined format based on a given configuration, such as a straightforward CMOS inverter. To accomplish this, the initial task is to meticulously define each port and allocate the appropriate class and use attributes to each one.

To establish the port configuration, you can utilize the Magic console, and here's a detailed breakdown of the steps involved:

Begin by opening the Magic Layout window.

Source the .mag file associated with your design, in this case, the inverter layout.

Navigate to the "Edit" menu and select "Text." This action will prompt a dialogue box to appear.

Within the dialogue box, double-click on the letter 'S' located at the I/O labels on the layout.

You will notice that the text field automatically populates with the appropriate string name and size for the port.

To finalize the port definition, ensure that the "Port enable" checkbox is selected, indicating that this element functions as a port. Additionally, make sure that the "Default" checkbox remains unchecked.

Your port configuration is now set up as illustrated in the figure.

![Screenshot from 2023-09-18 00-41-05](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/d3abdf44-bcd6-4ad2-b017-7b883832b21b)

![Screenshot from 2023-09-18 00-41-36](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/a9ffe778-3baf-4664-b939-f0e2e77b86f6)

```
port A class input
port A use signal

port Y class output
port Y use signal

port VPWR class inout
port VPWR use power

port VGND class inout
port VPWR use ground
```

![Screenshot from 2023-09-18 00-46-03](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/8ba212d6-77d6-40a3-92ab-7c255ee8cce8)

Custom cells to penLANE flow:

```

# Design
set ::env(DESIGN_NAME) "picorv32a"

set ::env(VERILOG_FILES) "$::env(DESIGN_DIR)/src/picorv32a.v"

set ::env(CLOCK_PORT) "clk"
set ::env(CLOCK_NET) $::env(CLOCK_PORT)

set ::env(GLB_RESIZER_TIMING_OPTIMIZATIONS) {1}

set ::env(LIB_SYNTH) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__typical.lib"
set ::env(LIB_SLOWEST) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__slow.lib"
set ::env(LIB_FASTEST) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__fast.lib"
set ::env(LIB_TYPICAL) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__typical.lib"

set ::env(EXTRA_LEFS) [glob $::env(OPENLANE_ROOT)/designs/$::env(DESIGN_NAME)/src/*.lef]

set filename $::env(DESIGN_DIR)/$::env(PDK)_$::env(STD_CELL_LIBRARY)_config.tcl
if { [file exists $filename] == 1} {
	source $filename
}

````
To Integrate standard cell into the OpenLANE flow:

```
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs
```
![Screenshot from 2023-09-18 00-49-10](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/825a116d-cb90-4d4a-aad4-59e3df686a5f)

**Custom cell naming and lef extraction**

Name of the custom cell :

```
sky130_vsdinv.mag
```
the modified config.json is

![Screenshot from 2023-09-18 21-58-57](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/bf4fa7df-22cc-4692-b72a-594ed15f1a0b)

In order to integrate the standard cell in the OpenLANE flow, invoke openLANE as usual and carry out following steps:

```
prep -design picorv32a 
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs
run_synthesis
```
![Screenshot from 2023-09-18 21-15-53](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/4cf4a934-b0ae-479b-a0df-d2fa80dce7e7)

![Screenshot from 2023-09-18 21-15-34](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/b3d0e67d-1a40-4b75-a45d-9587633f36dc)


To check the layout invoke magic
```
magic -T /home/vartika/.volare/sky130A/libs.tech/magic/sky130A.tech lef read tmp/merged.nom.lef def read results/placement/picorv32.def 
```

![Screenshot from 2023-09-18 21-10-37](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/d00fde54-ad65-44ed-aacc-70d11e79a3ff)

![Screenshot from 2023-09-18 21-11-02](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/89a2676e-fc67-4e82-8c08-399d945aaf79)

![Screenshot from 2023-09-18 21-14-41](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/5c2f8ff9-87c7-40b0-b9c3-aefc008d1ddd)

![Screenshot from 2023-09-18 22-07-49](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/761c9241-4fa6-471d-8bf3-18114f71cd04)


  **Introduction to delay Tables**
  In the context of digital integrated circuit (IC) design, delay tables (also known as delay models or delay tables) are data structures or lookup tables used to model the timing characteristics of logic gates, interconnects, and other components in the design. These tables capture information about the propagation delay and transition times of signals through various elements in the digital circuit. Delay tables are a fundamental component of the design process, as they help designers ensure that the circuit meets its timing requirements.

Here are key points about delay tables:

1. Propagation Delay: Delay tables provide information about the time it takes for a signal to propagate through a specific logic gate or interconnect. Propagation delay is typically measured from the time when an input signal reaches a certain threshold level to when the output signal reaches the same threshold level.

2. Transition Times: In addition to propagation delay, delay tables may include information about transition times, which represent how quickly a signal transitions from one logic state (e.g., low to high or high to low) to another.

3. Input Conditions: Delay tables are often organized based on input conditions. They specify the delay characteristics for different input patterns or signal conditions. For example, they may include tables for different input slew rates, voltage levels, or fanout conditions.

4. Library Cells: Delay tables are associated with library cells, which are predefined building blocks that represent standard logic gates (e.g., AND, OR, XOR) or flip-flops. Each library cell in the design library has its own delay table, capturing its timing characteristics under various conditions.

5. Technology Libraries: Semiconductor foundries provide technology libraries that include delay tables for their specific manufacturing processes. These libraries are essential for accurately modeling the behavior of cells in a given technology node.

6. Use in Timing Analysis: Delay tables are crucial for timing analysis in the design process. Timing analysis tools use these tables to estimate the worst-case and best-case delays for signals as they traverse the logic gates and interconnects in the design. This information helps ensure that the circuit meets its timing requirements, such as setup and hold times.

7. Incorporating Environmental Factors: Delay tables may also incorporate environmental factors, such as temperature and voltage variations, to account for variations in operating conditions. These factors can impact the timing behavior of the circuit.

8. Corner Cases: Designers often consider corner cases, which represent extreme conditions (e.g., worst-case voltage and temperature conditions), when analyzing delay tables to ensure that the design remains robust under all operating conditions.

9. Simulation and Synthesis: Delay tables play a critical role in simulation and synthesis processes. During simulation, they are used to accurately model the behavior of the design. In synthesis, they are considered to optimize the logic structure for timing and power constraints.

Overall, delay tables are an integral part of the design and analysis of digital ICs. They enable designers to evaluate and optimize the timing behavior of a circuit, ensuring that it meets performance requirements while accounting for variations and different operating conditions.

**Setup time and HOLD time**

Setup Time:

Definition: Setup time (Tsu) is the minimum amount of time that a data input signal (D) must be stable and valid before the clock signal (CLK) transitions from its inactive state (typically low) to its active state (typically high or rising edge).
Purpose: Setup time ensures that the data input has settled to its intended value before the clock edge arrives. This is crucial for preventing setup time violations, where the flip-flop or latch might capture a corrupted or invalid data value.
Violation: A setup time violation occurs when the data signal changes too close to or after the clock edge, potentially leading to incorrect data capture.
Setup Time Diagram

Hold Time:

Definition: Hold time (Th) is the minimum amount of time that the data input signal (D) must remain stable and valid after the clock signal (CLK) transitions from its active state back to its inactive state.
Purpose: Hold time ensures that the data input remains valid for a specified duration after the clock edge. This prevents hold time violations, which could lead to incorrect data capture or glitches in the output.
Violation: A hold time violation occurs when the data signal changes too soon after the clock edge, potentially causing the flip-flop or latch to capture an incorrect data value.
Hold Time Diagram

In summary:

**Setup Time:** It ensures that the data input is stable and valid before the clock edge, preventing late arrival of data.

**Hold Time:** It ensures that the data input remains stable and valid after the clock edge, preventing early removal of data.
Designers must consider setup and hold times when designing digital circuits to prevent timing violations. Violations can lead to unreliable operation, data corruption, and unpredictable behavior. Meeting these timing constraints often involves careful selection of flip-flops or latches and appropriate signal path delays to ensure that data transitions occur within the specified windows relative to clock edges. Advanced digital design tools and simulations are used to verify and optimize timing in complex digital systems.

![Screenshot from 2023-09-18 01-00-12](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/f4e11978-2985-4842-aa7c-55cc0d0d9fa1)


</details>

<details>
  <summary>
    Timing Analysis with ideal clocks using OpenSTA
  </summary>
	1. Setup time is the required time duration that the input data is stable before the triggering-edge of the clock.
2. If data is changing within this setup time window, the input data might be lost and not stored in the flip-flop as metastability might occur.
3. Metastability: When setup and hold time requirements are violated, the flip-flop state becomes unstable, and after an unpredictable duration, the state of the flip-flop can settle either way (1 or 0). This scenario is known as metastability.
As shown in the following figure, output Q1 passes through the slow logic and arrives late at the input D2 of FF2, which leads to setup time violation and the loss of the new data. Thus combinational delay must be less than clock frequency - setup time

	![Screenshot from 2023-09-18 01-00-12](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/c440c895-613f-4c96-9681-305fd69c946e)

**Clock Jitter**
Clock jitter is a phenomenon in digital and analog systems that refers to the variation or deviation in the timing of a clock signal's edges from their ideal positions. Clock jitter can impact the reliability and performance of electronic systems and is an important consideration in various applications, including data communication, signal processing, and integrated circuit (IC) design. 

![Screenshot from 2023-09-18 01-05-38](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/f5b31278-76a4-4d87-bc53-ac0250a6af09)


Different types of Jitter are as follows:

**1. Random Jitter:** Random jitter, also known as Gaussian jitter, results from random variations in the clock signal's edges. It is typically modeled as a statistical distribution.

**2. Deterministic Jitter:** Deterministic jitter is caused by specific, predictable sources of interference, such as power supply noise or crosstalk.

**3. Periodic Jitter:** Periodic jitter exhibits a regular pattern and is often related to the clock signal's harmonics or clock distribution network.

**4. Duty Cycle Distortion (DCD):** DCD is a type of jitter that occurs when the duty cycle of the clock signal deviates from 50%.

Configuring OpenSTA tool

Timing analysis is carried out outside the openLANE flow using OpenSTA tool. For this, pre_sta.conf is required to carry out the STA analysis. Invoke OpenSTA outside the openLANE:

```
sta pre_sta.conf
```

</details>

<details>
  <summary>
    Clock tree Synthesis TritonCTS and signal Integrity
  </summary>
	
**Clock Tree Synthesis**
	Clock tree synthesis (CTS) is a crucial step in the physical design of integrated circuits (ICs) or application-specific integrated circuits (ASICs). It involves the generation and optimization of a hierarchical network of clock distribution lines and buffers, often referred to as a "clock tree," to distribute the clock signal throughout the chip efficiently. The primary goal of CTS is to ensure that all sequential elements in the design (e.g., flip-flops, latches) receive the clock signal with minimal skew, adequate timing, and low power consumption. Here are the key aspects of clock tree synthesis:
1. The purpose of building a clock tree is to enable the clock input to reach every element and to ensure a zero clock skew.
2. H-tree is a common methodology followed in CTS. Before attempting a CTS run in TritonCTS tool, if the slack was attempted to be reduced in previous run, 
   the netlist may have gotten modified by cell replacement techniques. 
3. Therefore, the verilog file needs to be modified using the write_verilog command. In this stage clock is propagated and make sure that clock reaches each 
   and every clock pin from clock source with mininimum skew and insertion delay. Inorder to do this, we implement H-tree using mid point strategy.

The fig shown below shows the representation:

   ![Screenshot from 2023-09-18 01-20-11](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/cce4cd30-036a-4b63-b476-56a3ddce3a76)


The fig shown belows shows the buffering:
![Screenshot from 2023-09-18 01-21-14](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/59ddc993-191d-4f1b-90c5-56692e835730)

**Crosstalk and clock net shielding**

Crosstalk is a phenomenon in integrated circuits (ICs) and electronic systems where the electromagnetic fields associated with one signal (the aggressor) interfere with and affect the behavior of another nearby signal (the victim). This interference can lead to signal degradation, timing violations, and potential errors in digital circuits. Crosstalk can occur on any signal line, but it is particularly concerning on clock lines due to its potential impact on the synchronization of a digital system.

Clock net shielding, also known as clock shielding or clock tree shielding, is a technique used to mitigate crosstalk effects on clock lines, especially in high-speed and densely packed IC designs. Here's how crosstalk and clock net shielding are related:

**Types of Crosstalk: Crosstalk can be broadly categorized into two types:**

**1. Capacitive Crosstalk:** This occurs due to the coupling of electric fields between adjacent signal traces. It primarily affects the voltage levels of signals.
**2. Inductive Crosstalk:** This occurs due to the magnetic fields generated by current flow in nearby conductors. It primarily affects signal edges and can cause timing issues.

**Impact**
 Crosstalk is a significant concern in VLSI design due to the high integration density of components on a chip. Uncontrolled crosstalk can lead to data corruption, timing violations, and increased power consumption. Mitigation: VLSI designers employ various techniques to mitigate crosstalk, such as optimizing layout and routing, using appropriate shielding, implementing proper clock distribution strategies, and utilizing clock gating to reduce dynamic power consumption when logic is idle.
 
The fig shown below shows the representation:

![Screenshot from 2023-09-18 01-25-55](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/c063b225-449c-4b92-9a71-7d030d9b01d2)

</details>

# DAY 5 : Final steps for RTL2GDS using TriTON Route and OpenSTA
<details>
  <summary>
    Routing and Design rule check (DRC)
  </summary>

  **Maze Routing and Lee's Algorithm**
  The maze-routing algorithm you are referring to, often used in the context of chip multiprocessors (CMPs) and grid-based mazes, is designed to efficiently find routes or paths between two locations while minimizing overhead. This algorithm is essential in the field of integrated circuit design and routing, where the goal is to connect various components on a chip with minimal resource utilization. There are four steps of routing operations: Global Routing:

1. Establishes a high-level path for each net.
2. Focuses on overall routing topology.
3. Avoids obstacles and congestion areas.
   
 **Track Assignment:**

1. Divides routing area into tracks or channels.
2. Allocates tracks to specific nets.
3. Considers routing layer constraints.
   
**Detail Routing:**

1. Determines precise routing paths for each net.
2. Minimizes wirelength and avoids conflicts.
3. Adheres to design rules and constraints.
   
**Search and Repair:**

1. Identifies and resolves routing issues.
2. Handles design rule violations and congestion.
3. May require backtracking and iterative adjustments.
   
The Lee algorithm is a grid-based approach used for routing, particularly in chip design. It begins with designated source and target points and assigns labels to grid cells to find the shortest route between them, often favoring efficient L-shaped paths over zigzags. While valuable for global routing tasks, it can be time-consuming for complex designs with many pins. As a result, alternative algorithms have emerged to address scalability and specific routing challenges. The choice of routing method depends on the design's complexity and resource constraints.

![Screenshot from 2023-09-17 16-02-28](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/62f38122-6186-43fe-96c0-bb959e8a4d76)

**DRC**
Design Rule Checking (DRC) is a vital step in the physical design process, ensuring that a design adheres to manufacturing constraints dictated by the chosen process technology. Each technology comes with its specific set of rules, which become more numerous and intricate as manufacturing technology advances to smaller nodes. DRC verifies compliance with these predefined process rules provided by foundries, safeguarding against chip failures. It plays a critical role in defining a chip's quality. Key DRCs involve physical wire attributes like minimum width, spacing, and pitch, and they address issues like signal short violations by utilizing additional metal layers while rigorously checking vias, width, and spacing.Each semiconductor manufacturing process will have its own set of guidelines and margins to ensure that normal manufacturing variability won't lead to chip failure. below mentioned are few examples of DRC : Minimum width and spacing for metal, Minimum width and spacing for via, Fat wire Via keep out Enclosure, End of Line spacing, Minimum area, Over Max stack level, Wide metal jog, Misaligned Via wire, Different net spacing, Special notch spacing, Shorts violation, Different net Via cut spacing, Less than min edge length

![Screenshot from 2023-09-17 16-03-36](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/2b879116-f0b0-46b3-b126-ce3eef58bf28)

</details>

<details>
  <summary>
   Power Distribution network and Routing
  </summary>
  
  It is an infrastructure that provides a stable and reliable supply of electrical power to all components within an integrated circuit (IC) or chip. Generating a proper PDN is essential to ensure that all devices on the chip receive the required voltage levels with minimal noise and voltage drops.

The first step in generating the PDN is to plan the power grid. This involves determining the overall power requirements of the chip, including the voltage levels (typically VDD and VSS or ground) and the current needs of different functional blocks.

Designers also need to consider the power delivery network's topology, including the placement of power rails and ground lines, as well as the arrangement of power domains and their connectivity.

To stabilize the voltage and reduce noise, decapacitors (decaps) are strategically placed within the chip. Decaps act as local energy reservoirs and help compensate for sudden changes in current demand, especially during switching events.

The selection and placement of decaps are based on the expected load and voltage fluctuations in different regions of the chip.

we can check whether PDN has been created or no by check the current def environment variable:

```
echo $::env(CURRENT_DEF) and then gen_pdn

```


![Screenshot from 2023-09-17 18-00-51](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/f238b312-d1ec-484e-8aa8-7f067c633e29)

![Screenshot from 2023-09-17 18-02-03](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/afbc055b-15fe-432e-85f4-ee6d1240bb80)

Optimization techniques such as buffer insertion, voltage islands, and voltage scaling may be applied to improve PDN performance.After the chip's layout is complete, designers perform post-layout verification to confirm that the actual layout adheres to the PDN plan and design rules. Any discrepancies or issues are addressed.Once the PDN is successfully generated and verified, and all design rules are met, the chip design is considered ready for tape-out. The final layout data is sent to a semiconductor foundry for fabrication.

**Routing**
Routing refers to the process of determining the physical paths that electrical connections will take on the chip's layout. These connections, also known as metal traces or wires, are used to connect various components, such as logic gates, memory cells, and input/output (I/O) pads, on the chip. Routing plays a crucial role in determining the performance, power consumption, and manufacturability of the ASIC. 

![Screenshot from 2023-09-17 18-04-35](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/70c2c60d-f5f1-45a9-90ac-c252341f403d)

![Screenshot from 2023-09-17 18-05-20](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/9d2a216f-6343-445a-88f6-1415037fe448)

**Global Routing vs Detailed Routing**

Global routing and detailed routing are two distinct phases of the routing process in integrated circuit (IC) design. Each phase serves a specific purpose and involves different levels of abstraction and detail. Here's a comparison of global routing and detailed routing in ASIC or IC design:

**1. Purpose:**

Global Routing:

The primary goal of global routing is to determine approximate paths for connecting distant components or blocks on the chip.
It focuses on high-level considerations, such as wirelength optimization, congestion avoidance, and minimization of signal delays at a high level.

Detailed Routing:

Detailed routing follows global routing and aims to refine the connections by determining the exact placement of each wire segment.
It resolves conflicts, overlaps, and congestion at a finer level of detail.
The main purpose is to create a physically realizable layout that adheres to manufacturing constraints.

**2. Level of Detail:**

Global Routing:

Global routing operates at a higher level of abstraction.
It typically represents wires as abstract "tracks" without specifying their exact locations or paths.
The focus is on creating a high-level interconnection plan.
Detailed Routing:

Detailed routing operates at a lower level of abstraction.
It defines the precise positions and shapes of individual wires or metal traces.
It takes into account the detailed geometries of the chip's layout layers.

**3. Timing:**

Global Routing:

Global routing considers timing constraints but often as high-level constraints.
It aims to establish a feasible, high-level interconnect topology that meets global timing goals.
Detailed Routing:

Detailed routing refines the connections while ensuring that specific timing requirements are met.
It addresses fine-grained timing issues, such as signal delays and skew.
Wirelength Optimization:

Global Routing:

Global routing is responsible for an initial estimation of wirelength.
Its primary objective is to minimize the total wirelength across the entire chip.
Detailed Routing:

Detailed routing fine-tunes the wirelength and optimizes the paths for individual connections.
It may involve bending or shaping wires to fit the chip's layout.

**4. Complexity:**

Global Routing:

Global routing is computationally less intensive compared to detailed routing.
It is usually performed relatively quickly to provide a high-level interconnection plan.
Detailed Routing:

Detailed routing is more computationally demanding and time-consuming due to the need to consider precise geometries, manufacturing constraints, and timing details.

**5. Iteration:**

Global Routing:

Global routing is often performed as an initial step in the routing process.
The results of global routing can influence the subsequent detailed routing phase.
Detailed Routing:

Detailed routing may involve multiple iterations and refinements to optimize the placement of individual wires.
In summary, global routing and detailed routing are sequential phases in the routing process of IC design. Global routing provides a high-level interconnect plan, while detailed routing refines the plan to meet timing, manufacturing, and physical layout constraints. Both phases are essential for creating a reliable and manufacturable chip design.

![Screenshot from 2023-09-17 18-12-27](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/ed6fdd19-cea9-497f-b5cf-1b459a9dc039)


</details>

<details>
  <summary>
   Triton Route Features
  </summary>
  Feature-1 Honors pre-processed route guides

1. Adherence to Pre-Processed Route Guides: TritonRoute places significant emphasis on following pre-processed route guides.
2. This involves several actions: Initial Route Guide Analysis: TritonRoute analyzes the directions specified in the preferred route guides. If any non-directional routing guides are identified, it breaks them down into unit widths.
3. Guide Splitting: In cases where non-directional routing guides are encountered, TritonRoute divides them into unit widths to facilitate routing.
4. Guide Merging: TritonRoute merges guides that are orthogonal (touching guides) to the preferred guides, streamlining the routing process.
5. Guide Bridging: When it encounters guides that run parallel to the preferred routing guides, TritonRoute employs an additional layer to bridge them, ensuring efficient routing within the preprocessed guides.
6. Route guides are followed to satisfy inter- guide connectivity. Requirements of preprocessed route guides: Must have unit width and must be in the predefined direction. Directions of metal ensures minimum capacitances
   
   The tool takes into account the placement of standard cells, macro blocks, and other routing tracks as obstacles when determining the path of wires. It avoids collisions and ensures connectivity. TritonRoute employs routing algorithms to find the optimal paths for interconnections. The choice of algorithm can impact factors such as wirelength, signal delay, and power consumption.

TritonRoute-generated layouts are subject to physical verification steps to check for manufacturing-related issues, such as design rule violations and DRC errors.
**Triton route run for routing**
We start routing with : run_routing

This will do both global and detailed routing, this will take multiple optimization iterations until the DRC violation is reduced to zero. The zeroth iteration has 27426 violations and only at the 8th iteration was all violations solved.

![Screenshot from 2023-09-17 18-23-29](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/10a25da4-f8f9-47f3-ae88-23037ad50719)

</details>

