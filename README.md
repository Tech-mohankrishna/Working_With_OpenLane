# OPENLANE

## :book: ABOUT THE REPOSITORY
OpenLane is an automated RTL to GDSII flow based on several components including OpenROAD, Yosys, Magic, Netgen, CVC, SPEF-Extractor, KLayout and a number of custom scripts for design exploration and optimization. The flow performs all ASIC implementation steps from RTL all the way down to GDSII.

You can check out the documentation, including in-depth guides and reference manuals at [ReadTheDocs](https://openlane.readthedocs.io/).

<p align="center">
  <img src="https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/5ec41586-8e86-4ff9-b931-c496f565bbbd" >
</p>


# TABLE OF CONTENTS
+ [Day 1️⃣: Inception of open-source EDA, OpenLANE and Sky130 PDK](#introduction-to-risc-v-isa-and-gnu-compiler-toolchain)

+ [Day 2️⃣: Good Floorplan vs Bad floorplan & Introduction to Library Cells](#introduction-to-risc-v-isa-and-gnu-compiler-toolchain)

+ [Day 3️⃣: Design Library cell using Magic Layout & NGSpice Characterization](#introduction-to-risc-v-isa-and-gnu-compiler-toolchain)

+ [Day 4️⃣: Pre-Layout Timing Analysis & Importance of good clock tree](#introduction-to-risc-v-isa-and-gnu-compiler-toolchain)

+ [Day 5️⃣: Final Steps of RTL2GDS using tritonroute and OpenSTA](#introduction-to-risc-v-isa-and-gnu-compiler-toolchain)


# RTL to GDS2 Flow
The process from RTL (Register-Transfer Level) to GDS2 (Graphic Data System 2) in VLSI (Very Large Scale Integration) design involves several complex steps, each of which plays a crucial role in transforming a high-level hardware description into a final physical layout that can be fabricated as an ASIC (Application-Specific Integrated Circuit). Here's a detailed breakdown of these steps:

1. **RTL Design:**
   - **Specification:** The process begins with defining the functionality and behavior of the digital circuit. Engineers create a high-level specification of the desired ASIC, which outlines its input/output behavior and functionality.

   - **RTL Coding:** Engineers then write RTL code using hardware description languages like VHDL or Verilog. This code represents the digital logic and registers in the circuit and specifies how data flows between them.

2. **Synthesis:**
   - **Logic Synthesis:** RTL code is synthesized into a gate-level netlist. In this step, high-level RTL constructs are mapped to standard cells from a cell library, optimizing for factors like area, power, and timing.

3. **Floorplanning:**
   - **Area Allocation:** The chip's silicon area is divided into sections, and the location of major functional blocks is decided. This step ensures efficient space utilization, considering power and signal integrity.

4. **Placement:**
   - **Cell Placement:** Individual gates and standard cells are placed within the predefined areas. This step aims to optimize for timing, area, and power by carefully positioning cells.

5. **Clock Tree Synthesis:**
   - **Clock Distribution:** An efficient and balanced clock distribution network is designed to ensure that clock signals reach all parts of the chip synchronously.

6. **Routing:**
   - **Wiring:** Interconnections (wires) between the cells are established while adhering to design rules. This process involves global and detailed routing, optimizing for signal integrity and timing.

7. **Design Rule Checking (DRC):**
   - **Rule Verification:** The layout is checked against manufacturing design rules to ensure it complies with the fabrication process's constraints and limitations.

8. **Layout Versus Schematic (LVS) Verification:**
   - **Functionality Check:** LVS ensures that the physical layout matches the intended functionality described at the RTL level, confirming that the synthesized netlist corresponds to the layout.

9. **Extraction:**
   - **Parasitic Extraction:** Parasitic capacitance and resistance values are extracted from the layout and used for accurate timing analysis.

10. **Static Timing Analysis (STA):**
    - **Timing Verification:** STA analyzes the circuit's timing paths to ensure that setup and hold time constraints are met for all signals.

11. **Physical Verification:**
    - **DRC and LVS Recheck:** After any necessary corrections, DRC and LVS checks are run again to ensure compliance with design rules and functional correctness.

12. **GDS2 Generation:**
    - **GDS2 File Creation:** The final layout data is converted into GDS2 format, which is a standardized format for describing integrated circuit layouts.

13. **Tape-Out:**
    - **Fabrication Handoff:** The GDS2 files are submitted to a semiconductor foundry for manufacturing. This step involves preparing all required documentation and data for chip fabrication.

14. **Manufacturing and Testing:**
    - **Wafer Fabrication:** The semiconductor foundry produces silicon wafers with the designed ASICs.
    - **Testing:** The fabricated chips undergo various tests to ensure functionality and quality.

15. **Packaging:**
    - **Encapsulation:** The tested chips are packaged, providing protection and electrical connections to external devices.

16. **Final Testing:**
    - **System-Level Testing:** Packaged chips undergo system-level testing to verify their functionality in a real-world environment.

17. **Distribution:**
    - **Market Availability:** The ASICs are ready for market distribution and can be used in various electronic devices and systems.

Each step in this process is critical to ensuring that the final ASIC functions correctly, meets performance requirements, and can be manufactured reliably. The transformation from RTL to GDS2 involves meticulous planning, design, verification, and manufacturing expertise to produce cutting-edge integrated circuits.
