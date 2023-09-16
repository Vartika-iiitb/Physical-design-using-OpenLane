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

**1. RTL Synthesis, Technology Mapping, and Formal Verification:
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

</details>
