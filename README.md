# OpenLane

# :book: ABOUT THE REPOSITORY
OpenLane is an automated RTL to GDSII flow based on several components including OpenROAD, Yosys, Magic, Netgen, CVC, SPEF-Extractor, KLayout and a number of custom scripts for design exploration and optimization. The flow performs all ASIC implementation steps from RTL all the way down to GDSII.

You can check out the documentation, including in-depth guides and reference manuals at [ReadTheDocs](https://openlane.readthedocs.io/).


![image](https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/aeca0f43-27b6-46f4-a6cb-a817176f2e8e)



# TABLE OF CONTENTS
+ [Day 1️⃣: Inception of open-source EDA, OpenLANE and Sky130 PDK](#introduction-to-risc-v-isa-and-gnu-compiler-toolchain)
  	- Labwork for RISCV Toolchain
  	- RISCV GCC Compiler and Dissemble
  	- Spike Simulation and Debug
	- Integer Number Representation
  	- Labwork For Signed and Unsigned Numbers

+ [Day 2️⃣: Introduction to ABI and Basic Verification Flow](#introduction-to-abi-and-basic-verification-flow)
 	- Introduction to ABI
  	- Memmory Allocation for Double Words
  	- Load, Add and Store Instructions
  	- 32-Registers and their ABI Names
  	- Labwork using ABI Function Calls
  	- Simulate C Program using Function Call
  	- Lab to Run C-Program on RISCV-CPU

+ [Day 3️⃣: Introduction to Verilog RTL design and Synthesis](#introduction-to-verilog-rtl-design-and-synthesis)
  	- Introduction to open-source simulator iverilog
  	- Labs using iverilog and gtkwave
   		+ Introduction to lab
  	  	+ Introduction iverilog gtkwave 
	- Introduction to Yosys and Logic synthesis
   		+ Introduction to yosys
     		+ Introduction to logic synthesis
  	- Lab using Yosys and Sky130 PDKs
+ [Day 4️⃣: Timing Libs, Heirarchical VS Flat Synthesis, & Effecient Flop Coding Styles](#timing-libs-heirarchical-and-flat-synthesis)
  	- Introduction to timing dot libs
  	- Hierarchical vs Flat Synthesis
  	- Various Flop Coding Styles and optimization
   		+ Flop coding styles
  	  	+ Lab flop synthesis simulations
  	  	+ Interesting optimisations 
+ [Day 5️⃣: Combinational & Sequential Optimizations](#combinational-and-sequential-optimizations)
  	- Introduction to optimizations
  	- Combinational logic optimizations
  	- Sequential logic optimizations
  	- Sequential optimzations for unused outputs
+ [Day 6️⃣: GLS, blocking vs non-blocking and Synthesis-Simulation mismatch](#gls-blocking-vs-non-blocking-and-synthesis-simulation-mismatch) <br> 
  	- GLS, Synthesis-Simulation mismatch and Blocking/Non-blocking statements<br>
  	- Labs on GLS and Synthesis-Simulation Mismatch<br>
  	- Labs on synth-sim mismatch for blocking statement<br> 


