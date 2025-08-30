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
 
## 8.2 Wire-Bond Assembly Flow
 
## 8.3 Flip-Chip Assembly Flow
 
## 8.4 Fan-Out WLP Flow
 
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
# 11. Test Strategy
* **Wafer Probe:** Identify known-good die via probe cards and ATE.
* **AOST/OSAT Package Test:** Open/short screen, functional vectors, speed binning.
* **Burn-In:** Screen infant mortality under high T/V stress.
* **System-Level Test (SLT):** Run firmware/workloads to catch corner-case interactions.
# 10. Outlook of Semiconductor Packaging
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




lab1 documentation: https://github.com/rharishpersonal/SemiPackaging-course/blob/main/Lab%201%20Flip-Chip%20BGA.pdf
lab2 doc: https://github.com/rharishpersonal/SemiPackaging-course/blob/main/Lab%202%20Q3D%20Package.pdf
lab1 raw file: https://github.com/rharishpersonal/SemiPackaging-course/blob/main/flipchip_bga.aedt
lab2 raw file: https://github.com/rharishpersonal/SemiPackaging-course/blob/main/package_Q3D.aedt
