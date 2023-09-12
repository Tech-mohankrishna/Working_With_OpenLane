# ☑️ OPENLANE ☑️

## :book: ABOUT THE REPOSITORY
OpenLane is an automated RTL to GDSII flow based on several components including OpenROAD, Yosys, Magic, Netgen, CVC, SPEF-Extractor, KLayout and a number of custom scripts for design exploration and optimization. The flow performs all ASIC implementation steps from RTL all the way down to GDSII.

You can check out the documentation, including in-depth guides and reference manuals at [ReadTheDocs](https://openlane.readthedocs.io/).


<p >
  <img src="https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/52fd6324-b633-4ff6-bb55-b3c4f85a53f2" width=800 >
</p>


# TABLE OF CONTENTS
+ [Day 1️⃣: Inception of open-source EDA, OpenLANE and Sky130 PDK](#introduction-to-risc-v-isa-and-gnu-compiler-toolchain)

+ [Day 2️⃣: Good Floorplan vs Bad floorplan & Introduction to Library Cells](#introduction-to-risc-v-isa-and-gnu-compiler-toolchain)

+ [Day 3️⃣: Design Library cell using Magic Layout & NGSpice Characterization](#introduction-to-risc-v-isa-and-gnu-compiler-toolchain)

+ [Day 4️⃣: Pre-Layout Timing Analysis & Importance of good clock tree](#introduction-to-risc-v-isa-and-gnu-compiler-toolchain)

+ [Day 5️⃣: Final Steps of RTL2GDS using tritonroute and OpenSTA](#introduction-to-risc-v-isa-and-gnu-compiler-toolchain)


## RTL to GDS2 Flow
The process from RTL (Register-Transfer Level) to GDS2 (Graphic Data System 2) in VLSI (Very Large Scale Integration) design involves several complex steps, each of which plays a crucial role in transforming a high-level hardware description into a final physical layout that can be fabricated as an ASIC (Application-Specific Integrated Circuit). Here's a detailed breakdown of these steps:

### Invoking OpenLane
![image](https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/2f8b329a-da46-454a-a711-1d4791d2403c)

### Package Importing

![image](https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/561fde54-0b27-408c-a59b-a26c287f3f71)

### Design Preparation

![image](https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/4db3001f-c979-45dc-b27a-4f3054a10743)

### Synthesis

![image](https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/e6a2b457-f3d9-4294-bae2-cc6661268c5f)

### Floorplan

![image](https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/5b88266c-ae11-4963-a73a-4b565c4427d6)



## OpenLane ASIC Design Flow

<p >
  <img src="https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/3a371340-5198-430b-859e-a5a8bf46495d" width=600 >
</p>



Here's a detailed ASIC design flow using OpenLane and the associated tools and software:

**1. RTL Design:** Descri This phase involves creating the RTL description of the ASIC using hardware description languages (HDL) such as VHDL or Verilog.
   - **Tools/Software**: Any HDL simulator such as ModelSim, XSIM, or open-source alternatives like Icarus Verilog.

**2. Synthesis:** RTL code is synthesized into a gate-level netlist, optimizing for area, power, and timing.
   - **Tools/Software**: 
     - Yosys for synthesis.
     - ABC (A System for Sequential Synthesis and Verification) for technology mapping.
     - Cell libraries specific to the target process.
     - Yosys

**3. Floorplanning:** Define the chip's area and arrangement of major functional blocks.
   - **Tools/Software**: 
     - OpenROAD's TritonRoute for global placement.
     - Magic for floorplan visualization.

**4. Placement:** Position individual gates and standard cells optimally within the predefined areas.
   - **Tools/Software**: 
     - RePLace (REctangle PLACEr) for placement.
     - Magic for placement visualization.

**5. Clock Tree Synthesis:** Design a clock distribution network to ensure synchronous clock signals.
   - **Tools/Software**: 
     - OpenROAD's TritonCTS for clock tree synthesis.

**6. Routing:** Establish interconnections while adhering to design rules, optimizing for signal integrity and timing.
   - **Tools/Software**: 
     - FastRoute for global and detailed routing.
     - Magic for routing visualization.

**7. Design Rule Checking (DRC):**  Verify that the layout complies with manufacturing design rules.
   - **Tools/Software**: 
     - Magic for initial DRC checks.
     - OpenROAD's TritonRoute for DRC repair.

**8. Layout Versus Schematic (LVS) Verification:** Confirm that the physical layout matches the intended functionality described at the RTL level.
   - **Tools/Software**: 
     - Netgen for LVS checks.

**9. Parasitic Extraction:** Extract parasitic capacitance and resistance values from the layout for accurate timing analysis.
   - **Tools/Software**: 
     - QFlow's SPEF extraction tool for parasitic extraction.

**10. Static Timing Analysis (STA):** Analyze timing paths to ensure setup and hold time constraints are met.
    - **Tools/Software**: 
      - OpenSTA for static timing analysis.

**11. Physical Verification:** Perform a series of checks including DRC, LVS, and electrical rule checks (ERC).
    - **Tools/Software**: 
      - Magic for DRC and LVS checks.
      - Netgen for ERC checks.

**12. GDS2 Generation:** Convert the final layout data into GDS2 format for fabrication.
    - **Tools/Software**: 
      - Magic for GDS2 generation.







