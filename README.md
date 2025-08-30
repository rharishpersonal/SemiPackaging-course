**class notes:** https://github.com/rharishpersonal/SemiPackaging-course/blob/main/Semiconductor_Packaging_Notes.pdf
<br/>
**Semiconductor Packaging Workshop**
**Study Notes**
**Harish Kumar**
**Aug 15 – 24, 2025**
**Conducted by: VLSI System Design (VSD)**
# **1. Basics of Semiconductor Packaging**
Semiconductor packaging turns a fragile silicon die into a robust component that can be handled, assembled, powered, and cooled in real-world systems. Packaging provides protection, electrical input/output (I/O), mechanical stability, and thermal pathways.
## 1.1	What is Packaging and Why It Matters
  * After a silicon wafer is fabricated which is basically called as die, it contains thousands of tiny circuits (transistors)
  * These dies are extremely weak and cannot be used directly in a system
  * Packaging is the process of enclosing these dies in a protective structure that:
    * Provides mechanical protection
    * Enables electrical connectivity to the outside world like PCB
    * Helps in heat dissipation
* A silicon die fresh from the fab has microscopic pads for power and signals, no mechanical protection, and no native heat spreading capability. A package adds a substrate (carrier), external terminals (pins/balls/lands), an encapsulant (mold or lid), and thermal structures (heat spreaders, thermal vias, TIMs) to enable system integration.
## 1.2 Core Functions
* Protection: provides protection against mechanical shock, moisture contamination, corrosion, and ESD (electro-static discharge)
* Electrical Connectivity: provides pins, balls, or pads to connect power and high-speed signals from die to PCB
* Mechanical Support and Reliability: Provides structural integrity to the assembly to minimize mechanical stress and potential damage during thermal cycling, such as solder reflow processes.
* Thermal Management: Conducts and spreads heat away from active junctions to the ambient
## 1.3 Basic concept of a Package
* Die: The silicon chip
* Substrate: A base layer that routes signals and power
* Interconnects: Wire bonds or solder bumps
* Encapsulation: Mold compound for protection
* External Terminals: Pins, balls, or leads for PCB connection
# 2. Semiconductor Industry Ecosystem
  * Fabless: Design chips (e.g., Nvidia, Qualcomm)
  * Foundries: Fabricate wafers (e.g., TSMC, Samsung Foundry)
  * OSATs: Assembly and test specialists (e.g., ASE, Amkor)
  * IDMs: Vertically integrated, do everything (e.g., Intel, Micron).
# 3. Package Selection Criteria
* Application: Logic, memory, analog/mixed-signal, RF, power
* Electrical: I/O count, bandwidth/speed targets, signal integrity (loss, crosstalk), power delivery network PDN (IR drop, inductance, both these need to be low)
* Thermal: Power density, junction-to-ambient targets, allowable temperature rise, Heat spreaders
* Mechanical/Physical: Footprint, height, board-level constraints, reliability requirements
* Cost & Supply: Package/substrate cost, assembly yield, material availability
* Reliability: Moisture sensitivity, thermal cycling capability/stress, reflow.
# 4. Package Families and Mounting Styles
## 4.1	 Through-Hole and Surface-Mount Packages
* Through-Hole (TH): DIP, SIP, PGA — robust leads but lower I/O density
* Surface-Mount (SMT): SOIC, TQFP, QFN — compact footprints; QFN offers exposed thermal pads
## 4.2 Array and Advanced Packages
* BGA/LGA/FCBGA: Ball or land grid arrays on organic substrates, suitable for high-I/O SoCs
* CSP: Chip-scale packages approach die size; common in mobile chips
* PoP: package -on-package, vertically stacked logic + memory with short interconnects, all new SoC with LP5 memory have this kind of package
* SiP: Multi-die + passives in one module for space-constrained systems. This is going to be common for AI SoC going forward to meet the system performance requirements
# 5. Interconnect Technologies
## 5.1 Wire Bond
* Uses gold (Au)/copper (Cu)/Aluminum (Al) wires to connect die pads to lead frame/substrate pads.
* Advantages: maturity, cost, flexibility
* Considerations: loop inductance, SI limits at very high data rates, bond reliability.
## 5.2 Flip-Chip
* Die is flipped and joined to the substrate via solder bumps (e.g., SnAgCu) to minimize loop inductance
* Benefits: low inductance, high I/O density, short signal paths. Requires underfill for mechanical reinforcement.
## 5.3 Hybrid Bonding (Cu–Cu + Dielectric)
* Cu-Cu direct bonding + dielectric bonding, this enables die-to-die link and increases bandwidth density
* Enables <10 µm pitch for chiplets and 3D stacks.
## 5.4 Through-Silicon Vias (TSVs)
* Diameter: 5–10 µm, depth: 50–100 µm. Vertical vias for 3D stacks, enable direct interconnection between different layers
* Liner: etched and filled with Cu for conductivity.
* Advantages: reduces signal delay, power consumption, and form factor
# 6. Substrate and Interposer Technologies
## 6.1 Redistribution Layers (RDL)
Redistribution Layers are thin metal interconnect layers fabricated on the surface of a semiconductor die to reroute or “redistribute” the original input/output (I/O) pads to new locations. This process   enables finer pitch connections and allows the die to interface with advanced packaging technologies such as flip-chip, wafer-level chip scale packaging (WLCSP), and fan-out wafer-level packaging (FOWLP).   RDLs typically consist of multiple layers of patterned metal and dielectric materials, providing flexible routing for electrical signals, power, and ground connections.
## 6.2 Silicon and Glass Interposers
An interposer is a substrate that serves as an intermediate layer between a semiconductor die (or multiple dies) and the package substrate or printed circuit board (PCB). Its primary function is to        facilitate high-density electrical connections, signal routing, and sometimes power delivery between the dies and the underlying substrate.
* **Silicon Interposers:**
  * fabricated using semiconductor manufacturing processes and often incorporate Through-Silicon Vias (TSVs) for vertical electrical connections.
  * Offers Ultra-fine routing with TSVs for 2.5D integration (e.g., HBM + logic)
  * provide excellent thermal and mechanical properties but tend to be more expensive
* **Glass Interposers:**
  * use glass substrates instead of silicon
  * excellent dimensional stability, lower cost, excellent electrical insulation
  * limitations in thermal conductivity compared to silicon and require specialized processes
* **Organic Interposers:**
  * made from organic materials, such as epoxy resins reinforced with glass fibers, fabricated using standard PCB processes
  * cost-effective and scalable for high-volume production
  * Lower thermal conductivity and dimensional stability than glass/silicon
# 7. Wafer-Level Packaging (WLP)
WLP is an advanced semiconductor packaging technology in which the packaging process is performed at the wafer level, before the wafer is diced into individual chips (dies). Unlike traditional packaging,     where each die is packaged separately after dicing, WLP enables the creation of fully packaged, tested, and ready-to-mount devices directly on the wafer.
* **Fan-In WLP:** Pads redistributed within die area
* **Fan-Out WLP:** Pads extended beyond die area for higher I/O
* **Advantages:**
  * Smaller size, lower cost
  * Popular in smartphones and IoT
# 8. Manufacturing Flow (ATMP)
## 8.1 Wafer Preparation
<img width="320" height="277" alt="Wafer Preparation" src="https://github.com/user-attachments/assets/e945225e-24fc-4748-abdf-0e4e7c213bc8" />

<br><br>
## 8.2 Wire-Bond Assembly Flow
<img width="169" height="432" alt="Wire-Bond Assembly Flow" src="https://github.com/user-attachments/assets/df559cef-b989-450c-ad51-f2c161b33d30" />

<br><br>
## 8.3 Flip-Chip Assembly Flow
<img width="237" height="492" alt="Flip-Chip Assembly Flow" src="https://github.com/user-attachments/assets/86a17487-4b0c-45e5-bfec-a2ac1f693e82" />

<br><br>
## 8.4 Fan-Out WLP Flow
<img width="302" height="409" alt="Fan-Out WLP Flow" src="https://github.com/user-attachments/assets/4e7f7a8a-0165-4cae-9e28-d30c7df289ac" />

<br><br>
# 9. Package Testing and Electrical Functionality Checks
## 9.1 Foundry Testing Stages
* **Wafer Sort (Probe Test):**
  * Electrical testing of each die on the wafer before dicing
  * Identifies functional and non-functional dies; marks bad dies
 * **In-line Testing:**
   * Performed at various process steps during wafer fabrication
   * Monitors process control, detects defects early, and ensures yield
* **Parametric Testing:**
  * Measures electrical parameters (e.g., threshold voltage, leakage current) on test structures
  * Ensures process consistency and device reliability
## 9.2 OSAT Testing Stages
* **Incoming Material Inspection:**
  * Checks of quality and specifications of received wafers, substrates, and packaging materials
* **Pre-Assembly Testing:**
  * Optional electrical or visual inspection of wafers/dies before assembly to confirm integrity
* **Wafer Sort / Die Testing:**
  * Electrical testing of individual dies on the wafer, wafers are binned as per the performance
* **Post-Assembly Testing:**
 * Comprehensive electrical test of packaged devices to verify functionality, performance, and quality
* **Burn-In Test:**
  * Devices are subjected to elevated temperature and voltage to identify early-life failures.
* **Reliability Testing:**
  * Includes stress tests such as temperature cycling, humidity, ESD, and mechanical shock to ensure long-term reliability
* **System-Level Test (SLT):**
  * Run firmware/workloads to mimic the real-world applications with pre-defined application environment
* **visual and Automated Optical Inspection (AOI):**
  * Inspects packages for physical defects, marking errors, and surface quality
* **Quality Assurance (QA):**
  * Final checks for compliance with customer and industry standards before shipment
* **Outgoing Inspection:**
  * Ensures only tested and qualified products are shipped to customers.
# 10. Test Strategy
* **Wafer Probe:** Identify known-good die via probe cards and ATE.
* **AOST/OSAT Package Test:** Open/short screen, functional vectors, speed binning.
* **Burn-In:** Screen infant mortality under high T/V stress.
* **System-Level Test (SLT):** Run firmware/workloads to catch corner-case interactions.
# 11. Outlook of Semiconductor Packaging
* **Key Growth Factors:**
  * AI, HPC, and 5G/6G: Demand for high-bandwidth, low-latency interconnects.
  * Automotive Electrification: Power-dense modules for EVs.
  * Consumer Electronics: Miniaturization and energy efficiency
* **Technological Innovations:**
  * Advanced Integration: 2.5D and 3D Packaging
  * Cu-Cu Hybrid Bonding
  * Chiplet & Heterogeneous Integration
  * Vertical Power Delivery (VPD)
* **Thermal and Power Challenges:**
  * 3D IC Bottleneck
  * Thermal challenges in high-power and high-density packages
 <br><br>



# **lab1 documentation:** https://github.com/rharishpersonal/SemiPackaging-course/blob/main/Lab%201%20Flip-Chip%20BGA.pdf
## flipchip_bga
## Tool used: Ansys Elctronic Desktop (AEDT) 2022 R2
* **Package Dimensions:** 20x20x1.6mm
<img width="242" height="298" alt="Package Dimensions" src="https://github.com/user-attachments/assets/a4e0f976-0ef5-4d47-8158-3bf7991dd706" />

 
* **Die Dimensions:** 12x12mm, Power: 4mm, include heatsink
<img width="200" height="275" alt="Die Dimensions" src="https://github.com/user-attachments/assets/787c7798-d628-4497-8574-8aa8d9dbba64" />
 

* **Substrate:**
 <img width="210" height="276" alt="Substrate" src="https://github.com/user-attachments/assets/aace69d3-5a8f-4688-b577-09253c2c7a3f" />

* **Solder:** 15x15 rows
 <img width="277" height="360" alt="Solder" src="https://github.com/user-attachments/assets/3ffa764e-845a-401f-afec-2682bca2d9b1" />

<img width="780" height="504" alt="Solder1" src="https://github.com/user-attachments/assets/9f01297c-1b4e-4c65-ad7a-95d4588c71b5" />

* **Mesh Quality**
 * Face alignment
<img width="246" height="267" alt="Mesh Quality" src="https://github.com/user-attachments/assets/eaa766e9-d310-4a71-9118-4deaf296b22a" />

 
 * Volume
<img width="221" height="254" alt="Mesh Quality1" src="https://github.com/user-attachments/assets/837a0f53-c019-4f9f-b7fb-e896ec0a0772" />

 
 * Skewness
<img width="237" height="255" alt="Skewness" src="https://github.com/user-attachments/assets/a94cf5d0-54f9-4d16-8ed3-eae413e8c5c2" />
 	 	 

* **Final results:** heatsink was used in design so it brought down the temperature at die (junction)
<img width="780" height="553" alt="Final results" src="https://github.com/user-attachments/assets/44d0161f-5b9a-45ea-8257-eedd70b3a700" />

<img width="780" height="557" alt="Final results1" src="https://github.com/user-attachments/assets/606ca614-8cf4-47c0-b6fd-ebe7079b627d" />


 <br><br>
  
# **lab2 doc:** https://github.com/rharishpersonal/SemiPackaging-course/blob/main/Lab%202%20Q3D%20Package.pdf
## Q3D Package Cross-Section Modeling
* **Tool used:** Ansys Elctronic Desktop (AEDT) 2022 R2
* **Die:**
 * Material : Silicon (other options available: glass, Au)
 * Dimensions : 2 mm x 2 mm
 * Die Height : 150 micron

* **Substrate:**
 * Material : FR4  (other options available: laminate, BT_system)
 * Dimensions : 4 mm x 4 mm
 * Height : 400 micron

* **Die Attach:**
 * Material : Modified Epoxy, relative permittivity: 4.2 (other options available: FR4, kevalar)
 * Dimensions : 2mm x 2mm
 * Thickness : 100 micron

* **Die Bond Pads:**
 * Material : Copper
 * Dimensions : 0.2mm x 0.2mm
 * Thickness : 5 micron
 * Pitch: 0.2mm

* **Substrate Bond Pads:**
 * Material : Copper
 * Dimensions : 0.2mm x 0.2mm
 * Thickness : 10 micron
 * Pitch: 0.2mm

* **Bond Wire:**
 * Material : Au (other options available: Copper)
 * Type: JEDEC 5-point

* **Mold Compound:**
* Material : Epoxy_kevalar_xy (other options available: )
* Thickness : 1.5mm

## Tool images
* **project directry**
<img width="381" height="821" alt="project directry" src="https://github.com/user-attachments/assets/85476da8-3e09-41fa-9054-f668d96b3b79" />

* **wire bond**
<img width="780" height="595" alt="wire bond" src="https://github.com/user-attachments/assets/e6767d5a-d69b-42fb-ac49-2c80b19bfb23" />

* **wire bond with complete mold**
<img width="780" height="586" alt="wire bond with complete mold" src="https://github.com/user-attachments/assets/b7dfb42d-923e-4362-a1da-1c91d29576e4" />

* **wire bond with complete mold side view**
<img width="780" height="517" alt="wire bond with complete mold side view" src="https://github.com/user-attachments/assets/83dc4162-00fa-4c77-b053-1f76f62a9e51" />

  
 <br><br>


**lab1 raw file:** https://github.com/rharishpersonal/SemiPackaging-course/blob/main/flipchip_bga.aedt

**lab2 raw file:** https://github.com/rharishpersonal/SemiPackaging-course/blob/main/package_Q3D.aedt
