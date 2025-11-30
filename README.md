# Digital VLSI SoC Design – RISC-V Based SoC Documentation  
**Design Name:** `riscv_soc` – RISC-V System-on-Chip  
**Author:** Kiran Kumar Siripurapu  
**PDK:** Skywater 130nm (sky130A)  
**Tool Flow:** GCC (RISC-V), objdump, Yosys, OpenLane, Magic VLSI  
**Environment:** GitHub Codespaces / WSL  

**Final Status:** DRC Clean | STA Passed | CVC Matched | GDS Generated

---

### 1. Application → Compiler → RISC-V ISA  
| Explanation | Screenshot |
|------------|------------|
| C program used as input (Application level) | ![](submission/intro/01.png) |
| RISC-V GCC compilation output | ![](submission/intro/02.png) |
| RISC-V ISA (assembly) generated using objdump | ![](submission/intro/03.png) |

---

### 2. RTL Mapping and Architecture  
| Explanation | Screenshot |
|------------|------------|
| RISC-V instructions mapped to RTL hardware | ![](submission/intro/04.png) |
| RTL modules and block-level design | ![](submission/intro/05.png) |
| RTL block diagram continuation | ![](submission/intro/06.png) |
| Full RTL architecture view | ![](submission/intro/07.png) |

---

### 3. Synthesis – Yosys  
| Explanation | Screenshot |
|------------|------------|
| Synthesis report showing cell statistics | ![](submission/intro/03_synthesis.png) |

---

### 4. Floorplan  
| Explanation | Screenshot |
|------------|------------|
| Floorplan generated with core area + pins | ![](submission/intro/04_floorplan.png) |

---

### 5. Placement  
| Explanation | Screenshot |
|------------|------------|
| Standard cell placement (global + detailed) | ![](submission/intro/05_placement.png) |

---

### 6. Clock Tree Synthesis (CTS)  
| Explanation | Screenshot |
|------------|------------|
| CTS buffer insertion & clock tree structure | ![](submission/intro/06_cts.png.png) |

---

### 7. Routing  
| Explanation | Screenshot |
|------------|------------|
| Final routed layout (TritonRoute) | ![](submission/intro/07_routing.png) |

---

### 8. Final GDSII Layout – Magic  
| Explanation | Screenshot |
|------------|------------|
| Full GDS layout | ![](submission/intro/Full final GDS.png) |
| Zoomed-in layout view | ![](submission/intro/zoom in gds.png) |
| Standard cell zoom-in | ![](submission/intro/zoomed-in-cells.png) |

---

### 9. Signoff: DRC – Magic  
**Result: 0 Violations – DRC Clean**

| Explanation | Screenshot |
|------------|------------|
| Magic DRC clean result | ![](submission/intro/magic_drc_clean.png) |

---

### 10. Connectivity Verification (CVC)  
| Explanation | Screenshot |
|------------|------------|
| CVC connectivity match report | ![](submission/intro/CVC_report.png) |
| Additional CVC output | ![](submission/intro/CVC report.png) |

---

### 11. LVS Report  
| Explanation | Screenshot |
|------------|------------|
| Layout vs Schematic (Netgen) report | ![](submission/intro/lvs_report.png) |

---

### 12. Full-Chip LibreLane Scan  
| Explanation | Screenshot |
|------------|------------|
| Complete scan of GDS using LibreLane | ![](submission/intro/Complete_librelane_scan.jpg) |

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
The `riscv_soc` design has been fully processed through an open-source VLSI flow:  
- C → RISC-V ISA → RTL  
- RTL → Synthesis  
- Synthesis → PnR  
- PnR → Signoff  
- GDSII generated successfully  

**All checks passed:**  
- **DRC Clean**  
- **STA Met**  
- **CVC Verified**  

**Submitted by:** Kiran Kumar Siripurapu  
