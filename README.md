# ✅ OPENLANE ✅

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

<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>


# COURSE CONTENT







<details>
<summary>DAY 1 : Inception of opensource-EDA, Opennlane and Skywater130</summary>
<br>
# 📌 DAY-1

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



</details>



<details>
<summary>DAY 2 : Good Floorplan vs Bad Floorplan and Introduction to library cells</summary>
<br>

## Chip Floorplanning Considerations

### 1. Define Width and height of core and die

- ```Die``` : Structure that consists of core which is a small semiconductor material on which the fundamental circuit is fabricated.
- ```core``` : Structire that contains primary logic and functional components.

Whenever we come across the concepts of core and die, ```Utilisation factor``` plays an important role.
UTILISATION FACTOR = Area Occupied by the Netlist / Area of the core (usually 50%-70%)
ASPECT RATIO = Height / Width (1 = square, others = rectangle)

### 2. Define Location of Pre-Placed cells

```pre-placed cells``` : memories, clock gating cells, comparator, mux etc

- The arrangement of these IPs on chip is called FLOORPLANNING
- These IPs have user defined locations and hence are placed in chip before automated placement and routing. Therefore called pre-placed cells.
- Automated PnR tool places the remaining logical cells in design onto chip.

### 3. De-coupling capacitors

_____Problem_____
We know that all the combinational blocks are connected to Vdd and Vss for their operation. But when there is a large circuit with many resistors, then The capacitors in the logic might not get fully charged as there occurs voltage deop due to wire metal and the resistors present along the path. So after voltage drop, if the voltage obtained by the logic is within noise margin, then it works well but what if it doesn't? 

_____Solution_____
We use De-Coupling capacitors (A huge capacitance with voltage equal to that of supply voltage) that is placed close to the combinational logic. When the switching activity takes place, it detatches the circuit from main supply and this capacitor acts as power supply.

The local communication has been successfully eshtablished with the solution mentioned above. The global communication is taken care by power planning.

### 4. Power Planning

- Power planning during the Floorplanning phase is essential to lower noise in digital circuits attributed to voltage droop and ground bounce. Coupling capacitance is formed between interconnect wires and the substrate which needs to be charged or discharged to represent either logic 1 or logic 0.
- When a transition occurs on a net, charge associated with coupling capacitors may be dumped to ground. If there are not enough ground taps charge will accumulate at the tap and the ground line will act like a large resistor, raising the ground voltage and lowering our noise margin. To bypass this problem a robust PDN with many power strap taps are needed to lower the resistance associated with the PDN.

### 5. Pin Placement

- ```Pin placement``` is an essential part of floorplanning to minimize buffering and improve power consumption and timing delays.
- We usually place input pins on the left and output pins on the right
- for primary inputs and outputs, pin size may be small and for clock, the pin size would be large because clock should drive many cells so we need to make sure that the resistance is less.
- larger the area, lesser the resistance.
- ```Placement blockage``` is done inorder to makesure that no logic is placed along the area where the pin placement is carried out.

## Floorplan

```run_floorplan```


Now in openlane, enter ```run_floorplan``` and the results will be updated at the runs folder

![image](https://github.com/yagnavivek/PES_OpenLane_PD/assets/93475824/18b2cb6b-9915-4e58-b314-8d00260f47c7)

(0 0) in DIE AREA Indicates top-left corner co-ordinates and (660.685 671.405) indicates bottom-right corner of the die in micro-meters

To view the layout of the floorplan, use the command ```magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &```

- ```-T indicates``` techfile
- ```&``` is used to avoid the prompt that magic shows

![image](https://github.com/yagnavivek/PES_OpenLane_PD/assets/93475824/7804af4d-5e30-421f-8a81-4c3677c0af87)

## Library Binding and Placement

### 1. Bind the netlist with physical cells

- ```Library``` consists of cells, sizes of cells, various flavours and shapes of the cells, Timing, Power and delay information.
- Now, we have the floorplan, netlist and representation of components of netlist in library
- place all the components such that the timing is not disturbed and distribute them properly. 


### 2. Optimize Placement

- Some components may be located very far to their inputs which can disturb signal integrity (as wire length increases, RC value increases). Therefore we use repeaters(may be series of buffers) inorder to avoid signal loss but area loss comes into picture.
- Assuming that all the clock signals are working at ideal rate, we do the timing analysis if the current placement works good.

### 3. Placement

```run_placement```

![image](https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/0a04c130-a65b-4004-b0d0-2c1d66c95942)

## Cell Design Flow

Cell design is done in 3 parts:

1. **Inputs** - PDKs (Process design kits), DRC & LVS rules, SPICE models, library & user-defined specs.
2. **Design Steps** - Design steps of cell design involves Circuit Design, Layout Design, Characterization. The software GUNA used for characterization. The characterization can be classified as Timing characterization, Power characterization and Noise characterization.
3. **Outputs** - Outputs of the Design are CDL (Circuit Description Language), GDSII, LEF, extracted Spice netlist (.cir), timing, noise, power.libs, function.

### Standard cell Charachterization Flow

Standard Cell Libraries consist of cells with different functionality/drive strengths. These cells need to be characterized by liberty files to be used by synthesis tools to determine optimal circuit arrangement. The open-source software GUNA is used for characterization.
Characterization is a well-defined flow consisting of the following steps:

- Link Model File of CMOS containing property definitions
- Specify process corner(s) for the cell to be characterized
- Specify cell delay and slew thresholds percentages
- Specify timing and power tables
- Read the parasitic extracted netlist
- Apply input or stimulus
- Provide necessary simulation commands

### General Timing characterization parameters

#### Timing threshold definitions

- ```slew_low_rise_thr``` - 20% from bottom power supply when the signal is rising
- ```slew_high_rise_thr``` - 20% from top power supply when the signal is rising
- ```slew_low_fall_thr``` - 20% from bottom power supply when the signal is falling
- ```slew_high_fall_thr``` - 20% from top power supply when the signal is falling
- ```in_rise_thr``` - 50% point on the rising edge of input
- ```in_fall_thr``` - 50% point on the falling edge of input
- ```out_rise_thr``` - 50% point on the rising edge of ouput
- ```out_fall_thr``` - 50% point on the falling edge of ouput

These are the main parameters that we use to calculate factors such as propogation delay and transition time

- ```propogation delay ``` - time(out_*_thr) - time(in_*_thr)
- ```Transition time``` - time(slew_high_rise_thr) - time(slew_low_rise_thr)

[BACK TO TOP](https://github.com/yagnavivek/PES_OpenLane_PD#to-enter-the-automated-flow-use-these-commands)

</details>

<details>
<summary>DAY 3 :  Design library cell </summary>
<br>

## SPICE Deck creation for CMOS Inverter

SPICE deck contains the information of netlist such as:
- Connectivity Information
- Component values
- 'Nodes' identified
- 'Node' names

![image](https://github.com/yagnavivek/PES_OpenLane_PD/assets/93475824/fde8c66e-6547-49a2-bdad-478c812d5419)

### [CMOS_INVERTER.cir]()

```
*** MODEL DESCRIPTIONS ***
*** NETLIST DESCRIPTION ***
M1 out in vdd vdd pmos W=0.375u L=0.25u
M2 out in 0 0 nmos W=0.375u L=0.25u

cload out 0 10f

Vdd vdd 0 2.5
Vin in 0 2.5
*** SIMULATION Commands ***

.op
.dc Vin 0 2.5 0.05
*** include tsmc_025um_model.mod ***
.LIB "tsmc_025um_models.mod" CMOS_MODELS
.end
```

SPICE Simulation steps
```
cd <folder where the .cir file is present>
source CMOS_INVERTER.cir
run
setplot
dc1
display
plot out vs in
```

Observe the output. It should be symmetric ie., the threshold voltage should be at vdd/2 if it isnt, try to increase the PMOS width and run the simulation again. One of the important parameters tthat defines the **ROBUSTNESS** of the CMOS is ```Switching Threshold (Vm)``` @Vm : Vin = Vout

## Fabrication Process for a CMOS Inverter

Fabrication of CMOS Inverter is a 16-Mask process

### 1. Selecting the substrate 

- P-Type substrate with resistivity around (5-50 ohm) doping level (10^15 cm^-3) and orientation (100).
- Note that substrate doping should be less than well doping (used to fabricate NMOS and PMOS)

### 2. Create active resistance

This step creates pockets for NMOS and PMOS
1. Grow SiO2(~40nm) on Psub
2. deposit ~80nm Si3N4 on SiO2
3. deposit 1um layer of photoresist(used to define regions)
4. photolithography
5. etch out Si3N4 and SiO2 using a suitable solvent
6. Place the obtained structure in oxidartion furnace due to which field oxide is grown.This process is called ```LOCOS``` that is ```Local oxidation of silicon```
7. Etch out Si3N4 using hot phosphoric acid

### 3.NWel and PWel formation

- Apply photoresist, apply mask that covers NMOS
- Expose to UV, Wash, remove mask, appl boron(p-type) using Ion Implantation at an energy of 200Kev(for diffusion)
- repeat it for the other half using phosphorous @400Kev because phosphorous is heavier
- Wells have been created but the depth is low. Therefore subject it to high temperature furnace which increases the well depth.

### 4. Formation of Gate

- We repeat the step 3 but at low energy with p-type implant as boron @60Kev and n-type implant as Arsenic.
- Due to this The SiO2 is damaged as the dopants penetrate through it.
- Therefore original SiO2 is etched out using dilute HF solution and regrown to give high quality oxide(~10 nm thin)
- Finally for the gate to form, apply N-type ion implants for low gate resistance.
- Now mask on small width of Nwell and PWell above SiO2  and perform photolithography
- Gate Formation is Done

### 5. Lighlt Doped Drain Formation(LDD Formation)

- On the surface of SiO2 corresponding to NWell, apply photoresist, mask it, put phosphorous to make N-Implant on p-well(N-)
- Similarly do it for the other side using boron that forms (p-) implant
- This LDD has to be protected from further process
- so, Deposit 0.1um thick SiO2 on full structure and etch out using plasma anisotropic etching that results in formation of side wall spacers..

### 6. Source and Drain Formation

- Mask Nwell structure, deposit arsenic @75KeV that forms an N+ implant on Pwell
- use boron for P+ implant formation on Nwell
- Subject it to high temperature furnace that results in required thickness of N+,P+,N-,P- implants.

### 7. Steps to form contacts and interconnects

- Etch thin SiO2 oxide in HF solution
- Deposit Titanium of wafer surface using sputtering all over the structure
- Wafer heated at 600-700 degree in ambient N2 environment for 60 sec that reults in low resistance TiSi2 where the gate of both MOS is present.
- At the other places, TiN is formed that's used for local communication
- Etch off TiN on and half around gate structure of both MOS using RCA Cleaning

### 8. Higher level metal formation

- On the resulted structure, deposit a thick layer of (1um) SiO2 doped with P/B known as phosphoborosilicate glass
- To make the added surface plain, use CMP (Chemical Metal Polishing)
- For the creation of contact pins, proper holes with contacts have to be made
- This can be done using Al, W and TiN layer depositions.
- Deposit a layer of Si3N4 that acts as dielectric to protect the chip.

### 9. Final STructure

 ![image](https://github.com/yagnavivek/PES_OpenLane_PD/assets/93475824/0e355a75-55ff-4723-96ae-4abd5845697c)

## Inverter Layout using Magic

```
cd Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign
magic -T sky130A.tech sky130_inv.mag
```

## Exploring the Layout displayed by MAGIC

Select the specific layer/device by hovering over the object and pressing, s, iteratively, until you traverse the hierarchy to the specified object:

![image](https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/a040cf5b-77c0-49f9-9e96-05b21b71fbfd)


- select a region from the layout, go to the console and type ```what``` to display the information of selected area
- To select a region, place ```cursor``` on that point and  press```s```. More the number of times you press ```s```, higher the abstraction selected.

![image](https://github.com/yagnavivek/PES_OpenLane_PD/assets/93475824/fdd5bf6b-3483-4471-9b68-d98fa0b80af3)

refer to [inverter](https://github.com/nickson-jose/vsdstdcelldesign) to create layout for CMOS Inverter

### DRC Check

To check for DRC Errors, select a region (left click for starting point, right click at end point) and see the DRC column at the top that shows how many DRC errors are present.The Details of DRC Errors will be printed on the console.

![image](https://github.com/yagnavivek/PES_OpenLane_PD/assets/93475824/eebc0109-4408-40fa-a18e-ead67419cfa7)

For more information on DRC errors plase refer to: [DRC_Erros](https://skywater-pdk--136.org.readthedocs.build/en/136/)
For more information on how to fix these DRC errors using Magic please refer to: [fix_DRC](http://opencircuitdesign.com/magic/)


## Extracting PEX to SPICE with MAGIC

Select Full inverter layout. Then

![image](https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/1731e6ad-714a-43ee-8895-cddc501c605b)


![image](https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/4fab9429-4b95-4962-99d6-a9fd79566514)


The above file has details of inverter netlist but the sources and their values are not specified. So we have to modify the file.

- Grid size from the layout is 0.01u
- specify the library for MOS
- create VDD, VSS, Input pulse Va
- specify the type of analysis to be done

### Grid Size

![image](https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/ae7e38a1-95df-43ee-81ed-4fa2c97afeae)


## Modified Spice netlist

![image](https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/dead9f63-131a-4b89-9d87-5b3055d10dfd)


To run the spice netlist, run ```ngspice sky130_inv.spice``` and ```plot y vs time a```

![image](https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/78723ed0-f309-4461-8382-267e39d5bc93)


The results obtained from the graph are :
- Rise Transition : 0.0395ns
- Fall transition : 0.0282ns
- Cell Rise delay : 0.03598ns
- Cell fall delay : 0.0483ns

[BACK TO TOP](https://github.com/yagnavivek/PES_OpenLane_PD#to-enter-the-automated-flow-use-these-commands)

</details>

<details>
<summary>DAY 4 : Pre-Layout timing analysis and importance of good clock tree</summary>
<br>

## Extraction of LEF 

Place and routing (PnR) is performed using an abstract view of the GDS files generated by Magic. The abstract information will include metal and pin information. The PnR tool will use the abstract view information, formally defined as LEF information, to perform interconnect routing in conjunction to routing guides generated from the PnR flow.

- Technology LEF - Contains layer information, via information, and restricted DRC rules
- Cell LEF - Abstract information of standard cells

From PnR POV, We have to follow certain guidelines to get standard cell set
1. Input and output ports must lie on the intersection of vertical and horizontal tracks
2. Width of the standard cell should be odd multiples of the track pitch and height should be odd multiple of vertical track pitch


Track info can be found at :

``` ~/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/openlane/sky130fd_sc_hd/tracks.info```

![image](https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/9e4dc3b2-a47e-4c93-9edb-7aa227ce084b)


- 1st value indicates the offset and 2nd value indicates the pitch along provided direction

### Setting grid values using above file info

![image](https://github.com/yagnavivek/PES_OpenLane_PD/assets/93475824/b92d1c29-7d6a-4180-8754-25d768ce45f2)

Layout before setting grid info vs after setting grid info

![before_grid_info](https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/887cc1df-03fd-4596-92fc-f6162981cd0f)

![after_grid_info](https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/ec15a69d-7bfe-4256-8f79-35ed2140442a)

- From the above pic, its confirmed that the pins A and Y are at the intersection of X and Y tracks. So the first condition is met.
- The PR boundary is taking 3 grids on width and 9 grids on height which says that the 2nd condition is also met

## LEF Generation

Since the layout is perfect, we can generate the lef file

#### 1. save the modified layout (with new grid)
   - In console, type ```save sky130_vsdinv.mag```
   - This saves the modified layout in current working directory

#### 2. Open the file and extract LEF
   - Open using ``` magic -T sky130A.tch sky130_vsdinv.mag```
   - in the console opened, type ```lef write``` and a lef file will be generated

![image](https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/0e9d89de-6c57-4b98-8d8c-6d609b682b68)


#### 3. Plug the generated lef file into PICORV32a

To do this, we need the lef file, library file that has cells

![image](https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/99a5d5e5-87cf-44ff-bf5c-badb7ee4982c)


Change config file so that these libraries and lef file is used

![config](https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/dce8f252-e08e-4c40-b790-51084de2237d)



#### 4. Make sure the lef file is added

add the below 2 lines in the initial stage of interactive flow and ```run_synthesis```  to see if our inverter has been used and find timing violations if any.

![2lines](https://github.com/yagnavivek/PES_OpenLane_PD/assets/93475824/1c964f50-cefe-426f-9104-4562a1aab570)

![Screenshot from 2023-09-14 15-56-41](https://github.com/yagnavivek/PES_OpenLane_PD/assets/93475824/6ecd11e0-7b09-4966-9e36-897348896515)

The above figure shows that our vsdinv cell has been used in synthesis process

![Screenshot from 2023-09-14 15-57-05](https://github.com/yagnavivek/PES_OpenLane_PD/assets/93475824/f18b35db-10d4-4f47-b3b7-8a3ef657d57f)

since there is slack, we have to reduce it

VLSI engineers will obtain system specifications in the architecture design phase. These specifications will determine a required frequency of operation. To analyze a circuit's timing performance designers will use static timing analysis tools (STA). When referring to pre clock tree synthesis STA analysis we are mainly concerned with setup timing in regards to a launch clock. STA will report problems such as worst negative slack (WNS) and total negative slack (TNS). These refer to the worst path delay and total path delay in regards to our setup timing restraint. Fixing slack violations can be debugged through performing STA analysis with OpenSTA, which is integrated in the OpenLANE tool. To describe these constraints to tools such as In order to ensure correct operation of these tools two steps must be taken:

- Design configuration files (.conf) - Tool configuration files for the specified design
- Design Synopsys design constraint (.sdc) files - Industry standard constraints file

For the design to be complete, the worst negative slack needs to be above or equal to 0. If the slack is outside of this range we can do one of multiple things:

1. Review our synthesis strategy in OpenLANE
    - Enalbed CELL_SIZING
    - Enabled SYNTH_STRATEGY with parameter as "DELAY 1"
    - The synthesis result is :
  
    ![image](https://github.com/yagnavivek/PES_OpenLane_PD/assets/93475824/b4a26ed1-6ac8-449c-bc6e-31ed04470c4e)

    The slack has reduced a lot but still didnt meet the requirement. The sdc file used is [my_base.sdc](https://github.com/yagnavivek/PES_OpenLane_PD/blob/main/my_base.sdc) defined in [pre_sta.conf](https://github.com/yagnavivek/PES_OpenLane_PD/blob/main/pre_sta.conf) using the command ```sta pre_sta.conf```

   ![image](https://github.com/yagnavivek/PES_OpenLane_PD/assets/93475824/f7356fd8-9c7c-4d99-88d6-67ceadfa774f)

    The delay is high when the fanout is high. Therefore we can re-run synthesis by changing the value of ```SYNTH_MAX_FANOUT``` variable
    
2. Enable cell buffering 
3. Perform manual cell replacement on our WNS path with the OpenSTA tool

    - We can see which net is driving most outputs and replace the driver cell with larger form of its own kind

    ![image](https://github.com/yagnavivek/PES_OpenLane_PD/assets/93475824/f4e05f1d-0c2c-404a-8b43-6b82a097d73d)

4. Optimize the fanout value with OpenLANE tool

Since we have synthesised the core using our vsdinv cell too and as it got successfully synthesized, it should be visible in layout after ```run_placement``` stage which is followed after ```run_floorplan``` stage
![final-inver-image](https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/44453008-4016-4100-a940-1a33106cc5ca)


## Clock Tree Synthesis

- After all the above steps of fixing slack violations, as we have ```run_synthesis``` in openlane, it would have generated a mapped.v file in synthesis results but we have fixed all the violations using ```pre_sta.conf```. Therefore we write this netlist using ```write_verilog``` and replace the openlane generated mapped file ie., ```picorv32a.synthesis.v```

- now in the openlane flow, continue with ```run_flooorplan``` ```run_placement``` ```run_cts```

- To ensure that the cts step has added buffers and modified the netlist
  ![run_cts_directtory](https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/a80c7c04-6647-44cf-a7b8-b9bafc0431d8)


## Post CTS- STA Analysis

OpenLANE has the OpenROAD application integrated into its flow. The OpenROAD application has OpenSTA integrated into its flow. Therefore, we can perform STA analysis from within OpenLANE by invoking OpenROAD.

In OpenROAD the timing analysis is done by creating a .db database file. This database file is created from the post-cts LEF and DEF files. To generate the .db files within OpenROAD:
- Invoke OpenRoad
- Read lef file from tmp folder of runs
- Read def file from results of cts
- write db file
- Read the generated db file
- Read the cts generated verilog file
- read min and max liberty file
- set the clocks
- generate the reports

![openroad_steps](https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/6fae45f8-8027-4313-9deb-51af99005568)
![my_base](https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/222858cb-6cb5-4ab5-aeba-478b9e5787ff)

The results wont meet the timing because we are using min and max lib files and openroad doesnot support multi corner optimisation. Therefore we do it using only typical corner lib

![my_base_results](https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/07ffd710-8025-4f20-8359-f74ef6593ea7)


We have to ensure that the skew is withing 10% of clock period ie., should be less than 1.6 in my case

![hold_setup](https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/90e3d0fc-aa81-4692-a49f-f4c200ee3b4e)


[BACK TO TOP](https://github.com/yagnavivek/PES_OpenLane_PD#to-enter-the-automated-flow-use-these-commands)

</details>

<details>
<summary>DAY 5 : Final steps for RTL2GDSII</summary>
<br>

## Power Distribution Network

After generating our clock tree network and verifying post routing STA checks we are ready to generate the power distribution network ```gen_pdn``` in OpenLANE:

The PDN feature within OpenLANE will create:

- Power ring global to the entire core
- Power halo local to any preplaced cells
- Power straps to bring power into the center of the chip
- Power rails for the standard cells


![gen_pdn](https://github.com/Tech-mohankrishna/Working_With_OpenLane/assets/57735263/37102347-af71-43bd-95ed-9f1b2aae91ac)

Note: The pitch of the metal 1 power rails defines the height of the standard cells

## Global and Detailed Routing

OpenLANE uses TritonRoute as the routing engine ```run_routing``` for physical implementations of designs. Routing consists of two stages:

- Global Routing - Routing guides are generated for interconnects on our netlist defining what layers, and where on the chip each of the nets will be reputed
- Detailed Routing - Metal traces are iteratively laid across the routing guides to physically implement the routing guides

If DRC errors persist after routing the user has two options:

- Re-run routing with higher QoR settings
- Manually fix DRC errors specific in tritonRoute.drc file

## SPEF Extraction

After routing has been completed interconnect parasitics can be extracted to perform sign-off post-route STA analysis. The parasitics are extracted into a SPEF file. The SPEF extractor is not included within OpenLANE as of now.

```
cd ~/Desktop/work/tools/SPEFEXTRACTOR
python3 main.py <path to merged.lef in tmp> <path to def in routing>
```

The SPEF File will be generated in the location where def file is present

[BACK TO TOP](https://github.com/yagnavivek/PES_OpenLane_PD#to-enter-the-automated-flow-use-these-commands)


</details>





























