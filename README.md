# Digital VLSI SoC Design – RISC-V Based SoC Documentation  
**Design Name:** `riscv_soc` – RISC-V System-on-Chip  
**Author:** Kiran Kumar Siripurapu  
**PDK:** Skywater 130nm (sky130A)  
**Tool Flow:** GCC (RISC-V), objdump, Yosys, OpenLane, Magic VLSI  
**Environment:** WSL/LibreLane  

**Final Status:** DRC Clean | STA Passed | CVC Matched | GDS Generated

---

### 1. Application → Compiler → RISC-V ISA  
These steps validate the *software-to-hardware* path: how C code becomes RISC-V instructions that the SoC must execute.

| Explanation | Screenshot |
|------------|------------|
| RISC-V SoC architecture with foundry IPs integrated | ![](submission/intro/01.png) |
| C code compiled with `riscv64-unknown-elf-gcc` | ![](submission/intro/02.png) |
| Final RISC-V ISA generated using `objdump -d` | ![](submission/intro/03.png) |

Key Outcome:  
The exact sequence of machine instructions executed by the RISC-V core is confirmed.

---

### 2. RTL Mapping and Architecture  
This section shows how RISC-V instructions are implemented in hardware using RTL modules.

| Explanation | Screenshot |
|------------|------------|
| Machine instructions connected to RTL datapath | ![](submission/intro/04.png) |
| Module-level breakdown of CPU, memory, and peripherals | ![](submission/intro/05.png) |
| Control + datapath integration | ![](submission/intro/06.png) |
| Overall SoC RTL block architecture | ![](submission/intro/07.png) |

Key Outcome:  
Logical architecture is verified before physical implementation.

---

### 3. Synthesis – Yosys  
RTL is converted to a gate-level netlist using sky130 standard cells.

| Explanation | Screenshot |
|------------|------------|
| Gate count, cell usage, and Yosys statistics | ![](submission/intro/03_synthesis.png) |

Key Outcome:  
RTL is validated, optimized, and mapped to real hardware cells.

---

### 4. Floorplan  
Defines die size, rows, pin locations, and power grid — the foundation for PnR.

| Explanation | Screenshot |
|------------|------------|
| Core area created with IO pins + power grid | ![](submission/intro/04_floorplan.png) |

Key Outcome:  
Legal placement area is created ensuring proper routing and power distribution.

---

### 5. Placement  
Standard cells are placed while respecting timing and congestion constraints.

| Explanation | Screenshot |
|------------|------------|
| Standard cell global + detailed placement | ![](submission/intro/05_placement.png) |

Key Outcome:  
Cells are optimally placed for routing and timing closure.

---

### 6. Clock Tree Synthesis (CTS)  
Inserts buffers/inverters to balance clock arrival across all sequential elements.

| Explanation | Screenshot |
|------------|------------|
| Clock buffers inserted, tree balanced | ![](submission/intro/06_cts.png.png) |

Key Outcome:  
Clock skew and latency are controlled to meet timing.

---

### 7. Routing  
Generates complete metal interconnect while obeying DRC rules.

| Explanation | Screenshot |
|------------|------------|
| Final routed design using TritonRoute | ![](submission/intro/07_routing.png) |

Key Outcome:  
All nets connected with zero routing violations.

---

### 8. Final GDSII Layout – Magic  
Complete manufactured layout including all layers.

| Explanation | Screenshot |
|------------|------------|
| Full-chip GDS exported from OpenLane | ![](submission/intro/Full-final-GDS.png) |
| Close-up view showing metal routing and vias | ![](submission/intro/zoom_in_gds.png) |
| Zoomed standard cell region | ![](submission/intro/zoomed-in-cells.png) |

Key Outcome:  
Tapeout-ready GDS validated visually.

---

### 9. Signoff: DRC – Magic  
**Result: 0 Violations – DRC Clean**

| Explanation | Screenshot |
|------------|------------|
| All design rules satisfied | ![](submission/intro/magic_drc_clean.png) |

Key Outcome:  
Layout is manufacturable with no rule violations.

---

### 10. Connectivity Verification (CVC)  
Matches extracted layout netlist with synthesized netlist.

| Explanation | Screenshot |
|------------|------------|
| CVC matched all nets (no shorts/opens) | ![](submission/intro/CVC_report.png) |
| Additional connectivity result | ![](submission/intro/CVC report.png) |

Key Outcome:  
Layout is electrically equivalent to RTL design.

---

### 11. LVS Report  
Ensures layout = schematic with no mismatches.

| Explanation | Screenshot |
|------------|------------|
| Netgen LVS clean report | ![](submission/intro/lvs_report.png) |

---

### 12. Full-Chip LibreLane Scan  
| Explanation | Screenshot |
|------------|------------|
| External verification of final GDS | ![](submission/intro/Complete_librelane_scan.jpg) |

---

### Final Deliverables  
| File | Location |
|------|----------|
| GDSII | `submission/gds/riscv_soc.gds` |
| DEF | `submission/def/riscv_soc.def` |
| Synthesized Netlist | `submission/netlist/riscv_soc.v` |
| Reports | `submission/reports/*` |

---

### Conclusion  
The `riscv_soc` design has successfully completed:  
- C → ISA → RTL mapping  
- Synthesis  
- Floorplan, Placement, Clocking  
- Routing and Signoff  
- DRC, STA, CVC, LVS verification  
- GDSII fabrication output  

**All verification checks passed.**  
**Design is ready for manufacturing.**

**Submitted by:** Kiran Kumar Siripurapu  
