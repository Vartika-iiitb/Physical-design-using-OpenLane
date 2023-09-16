# Advanced Physical-design-using-OpenLane

<details>
  <summary>
      Day 1 : Inception of open-source EDA ,OpenLANE and sky130 pdk
  </summary>
  
  **How to talk to computers**
  
  The QFN-48 package is a type of surface-mount integrated circuit (IC) package that is used in various electronic devices, including some Arduino-compatible microcontrollers and other components. "QFN" stands for "Quad Flat No-Lead," which describes the package's physical characteristics. Here's what some of these terms mean:

 1. Quad: The package has four sides or corners, typically with a lead or pad on each corner.

 2. Flat: The package has a flat bottom, which makes it suitable for surface-mount soldering onto a printed circuit board (PCB).

 3. No-Lead: Unlike traditional dual in-line packages (DIP) or surface-mount packages with visible leads or pins, QFN packages have no visible external leads or pins. Instead, they have small metal pads on the bottom of the package.

4. 48: The "48" in QFN-48 refers to the total number of pads or leads on the package. These pads are used for electrical connections between the IC and the PCB.

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


**Introduction to RisCV**

RISC-V (pronounced "risk-five") is an open-source instruction set architecture (ISA) for designing and building computer processors and related hardware components. It's named after the "Reduced Instruction Set Computing" (RISC) philosophy, which aims to simplify processor designs by using a smaller set of instructions that execute quickly and efficiently.

![Screenshot from 2023-09-16 18-36-36](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/efe64a42-2531-4f17-86d4-cc9c5940bfa0)

**From Software Applications to Hardware**
In the realm of software applications, tasks are executed by the central processing unit (CPU) of a computer or device. Software programs provide instructions for the CPU to follow, and the CPU performs calculations, data processing, and various other operations based on these instructions. While software is flexible and can be updated easily, it may not always provide the highest level of performance or efficiency, especially for demanding or specialized tasks.

The benefits of this transition from software to hardware include faster execution of tasks, lower power consumption, and the ability to handle specialized workloads with greater efficiency. However, it also means that the functionality is fixed and less adaptable compared to software, which can be updated or changed more easily.

The Figure shown below shows the representation :

![Screenshot from 2023-09-16 18-40-16](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/e4bc8336-ee32-4fff-b742-5c0a56dcbcf3)

**SoC Design and OpenLANE**
![Screenshot from 2023-09-16 19-05-17](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/698b6b22-612a-4e4c-b6d3-15c03b3a593b)
![Screenshot from 2023-09-16 19-17-39](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/86bc8569-9438-4483-ace2-343088b100f3)

![Screenshot from 2023-09-16 19-05-11](https://github.com/Vartika-iiitb/Physical-design-using-OpenLane/assets/140998716/3f4ede54-22ba-486b-a214-e573dd3dfdd8)

</details>
