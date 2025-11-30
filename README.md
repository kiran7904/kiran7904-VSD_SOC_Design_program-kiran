# Digital VLSI SoC – RISC-V Full Flow Documentation  
**Design Name:** `riscv_soc` – RISC-V Based System-on-Chip  
**Author:** Kiran Kumar Siripurapu  
**PDK:** Skywater 130nm (sky130A)  
**Tool Flow:** GCC (RISC-V), objdump, Yosys, OpenLane/Qflow, Magic VLSI  
**Environment:** Linux / WSL  

**Final Output:** Layout Generated | RTL Verified | ISA Verified | Ready for Signoff

---

### 1. C Program (Application Source)
| Explanation | Screenshot |
|------------|------------|
| C code used as the starting point of the flow | ![C code](submission/images/c_code.png) |

---

### 2. RISC-V Compiler Output  
| Explanation | Screenshot |
|------------|------------|
| RISC-V GCC compiling the C code | ![Compiler output](submission/images/compiler_output.png) |
| Assembly (ISA) dump using `objdump` | ![ISA dump](submission/images/isa_dump.png) |

---

### 3. RTL and Architecture Mapping  
| Explanation | Screenshot |
|------------|------------|
| RISC-V instructions mapped to RTL (picorv32) | ![RTL mapping](submission/images/rtl_mapping.png) |
| RTL hierarchy and modules used in SoC | ![RTL hierarchy](submission/images/rtl_hierarchy.png) |

---

### 4. Synthesis Output  
| Explanation | Screenshot |
|------------|------------|
| Yosys synthesis result showing cell statistics | ![Synthesis stats](submission/images/synthesis_stats.png) |
| Netlist generated after synthesis | ![Netlist](submission/images/netlist_view.png) |

---

### 5. Floorplanning  
| Explanation | Screenshot |
|------------|------------|
| Initial floorplan generation | ![Floorplan](submission/images/floorplan.png) |
| Power planning (straps, rails, rings) | ![Power plan](submission/images/power_plan.png) |

---

### 6. Placement  
| Explanation | Screenshot |
|------------|------------|
| Standard cell global placement | ![Global placement](submission/images/global_placement.png) |
| Detailed placement completed | ![Detailed placement](submission/images/detailed_placement.png) |

---

### 7. Clock Tree Synthesis (CTS)  
| Explanation | Screenshot |
|------------|------------|
| CTS report summary | ![CTS](submission/images/cts_report.png) |

---

### 8. Routing  
| Explanation | Screenshot |
|------------|------------|
| Routed layout (TritonRoute) | ![Routing](submission/images/routing.png) |
| Congestion-free final routing | ![Routing clean](submission/images/routing_clean.png) |

---

### 9. Final Layout – Magic VLSI  
| Explanation | Screenshot |
|------------|------------|
| Full-chip layout | ![Full layout](submission/images/full_layout.png) |
| Zoomed view of standard cells | ![Cells](submission/images/cell_zoom.png) |
| Metal layers + routing visualization | ![Metal layers](submission/images/metal_layers.png) |

---

### 10. Signoff Checks  
| Explanation | Screenshot |
|------------|------------|
| DRC run in Magic | ![DRC](submission/images/drc.png) |
| STA (Setup & Hold Slack) | ![STA](submission/images/sta.png) |
| CVC connectivity check | ![CVC](submission/images/cvc.png) |

---

### 11. Final Output Files  
| Deliverable | File |
|-------------|------|
| GDSII | `submission/gds/riscv_soc.gds` |
| DEF | `submission/def/riscv_soc.def` |
| Netlist | `submission/netlist/riscv_soc.v` |
| Reports | `submission/reports/*` |

---

### Conclusion  
The `riscv_soc` design successfully demonstrates:  
- Complete software → hardware mapping  
- RISC-V ISA → RTL correlation  
- Full open-source synthesis and PnR flow  
- Clean layout visualization  
- Ready for signoff verification steps  

**Submitted by:** Kiran Kumar Siripurapu  
