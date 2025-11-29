# Digital VLSI SoC Design and Planning – Final Project Report  
**Design Name:** `spm` – Small Processing Module  
**Author:** Kiran Kumar Siripurapu  
**PDK:** Skywater 130nm (sky130A)  
**Tool Flow:** OpenLane 2 – Complete RTL to GDSII  
**Environment:** GitHub Codespaces  

**Final Signoff:** DRC = 0 Errors | STA = Timing Met | CVC = Passed | GDSII Ready  

---

### 1. RTL Source File
| Explanation                                      | File / View                                      |
|--------------------------------------------------|--------------------------------------------------|
| Original Verilog RTL used without any changes    | [submission/RTL/spm.v](submission/RTL/spm.v)     |

---

### 2. OpenLane Reports Directory Structure
| Explanation                                               | Screenshot                                              |
|-----------------------------------------------------------|---------------------------------------------------------|
| Complete OpenLane run reports directory after successful flow | ![OpenLane reports directory](submission/images/OpenLane%20run%20reports%20directory%20view.png) |

---

### 3. Final Layout Views in Magic VLSI
| Explanation                                               | Layout Screenshot                                       |
|-----------------------------------------------------------|---------------------------------------------------------|
| Full final chip layout after routing                      | ![Full Layout](submission/images/magic_layout_full.png) |
| Zoomed-out view of entire die                             | ![Zoomed-out](submission/images/magic_layout_full_zoom.png) |
| Close-up view of standard cells and routing               | ![Standard cell zoom](submission/images/magic_layout_zoom.png) |
| Custom ALU block layout (zoomed-out)                      | ![Custom ALU](submission/images/Custom%20ALU%20layout%20(zoomed-out%20view).png) |
| Parasitic extraction log + simple ALU layout side-by-side | ![Extraction + ALU](submission/images/Extraction%20log%20+%20simple_alu%20layout%20(Magic%20side-by-side).png) |

---

### 4. Design Rule Check (DRC) – Magic VLSI  
**Result: 0 Violations → DRC Clean**

| Explanation                                               | Screenshot                                              |
|-----------------------------------------------------------|---------------------------------------------------------|
| Magic DRC menu opened                                     | ![DRC menu](submission/images/magic_drc_menu.png)       |
| DRC executed in tkcon console – showing 0 errors          | ![DRC 0 errors](submission/images/tkcon_drc_check.png)  |
| Final confirmation: Zero DRC violations                   | ![Zero DRC](submission/images/zero_drc.png)             |

**DRC Report:** [drc.rpt](submission/OpenLane/reports/signoff/drc.rpt)

---

### 5. Static Timing Analysis (STA) – OpenSTA  
**Result: Setup & Hold Met – Positive Slack**

| Explanation                                               | Screenshot / Report                                     |
|-----------------------------------------------------------|---------------------------------------------------------|
| Terminal output showing positive setup & hold slack       | ![STA positive slack](submission/images/sta_summary_terminal-slack.png) |
| STA summary report file content                           | ![STA file](submission/images/sta_summary_file.png)     |

**Key STA Reports:**
- [Summary: [31-rcx_sta.summary.rpt](submission/OpenLane/reports/signoff/31-rcx_sta.summary.rpt)
- Setup: [31-rcx_sta.max.rpt](submission/OpenLane/reports/signoff/31-rcx_sta.max.rpt)
- Hold: [31-rcx_sta.min.rpt](submission/OpenLane/reports/signoff/31-rcx_sta.min.rpt)

---

### 6. Connectivity Verification Check (CVC)
| Explanation                                               | Screenshot                                              |
|-----------------------------------------------------------|---------------------------------------------------------|
| CVC passed – layout netlist matches synthesized netlist   | ![CVC passed](submission/images/cvc_report.png)       |

**CVC Report:** [spm.rpt](submission/OpenLane/reports/signoff/spm.rpt)

---

### 7. Bonus: Full-Chip Scan using LibreLane
| Explanation                                               | Full Scan                                               |
|-----------------------------------------------------------|---------------------------------------------------------|
| Complete top-level scan of final GDSII scan               | ![LibreLane full scan](submission/images/Complete_librelane_scan.jpg) |

---

### 8. Final Tapeout-Ready Files
| Deliverable                    | Direct Link                                                                 |
|-------------------------------|-----------------------------------------------------------------------------|
| Final GDSII (fabrication ready) | [spm.gds](submission/OpenLane/gds/spm.gds)                                  |
| Final DEF                       | [spm.def](submission/OpenLane/def/spm.def)                                  |
| RTL Source                      | [spm.v](submission/RTL/spm.v)                                               |

---

### 9. All Signoff Reports – Quick Access
| Report Name               | Link                                                                                   |
|---------------------------|----------------------------------------------------------------------------------------|
| DRC Report                | [drc.rpt](submission/OpenLane/reports/signoff/drc.rpt)                                 |
| STA Summary               | [31-rcx_sta.summary.rpt](submission/OpenLane/reports/signoff/31-rcx_sta.summary.rpt)   |
| STA Setup Report          | [31-rcx_sta.max.rpt](submission/OpenLane/reports/signoff/31-rcx_sta.max.rpt)           |
| STA Hold Report           | [31-rcx_sta.min.rpt](submission/OpenLane/reports/signoff/31-rcx_sta.min.rpt)           |
| CVC Report                | [spm.rpt](submission/OpenLane/reports/signoff/spm.rpt)                                 |
| IR Drop Report (VPWR)     | [32-irdrop-VPWR.rpt](submission/OpenLane/reports/signoff/32-irdrop-VPWR.rpt)           |

---

### Conclusion  
The `spm` design has been successfully taken through a **complete open-source ASIC flow** using OpenLane and Sky130 PDK.  

**All signoff criteria fully satisfied:**  
**DRC Clean (0 errors)**  
**Timing Closed (Setup & Hold met)**  
**CVC Passed**  
**Tapeout-ready GDSII generated**

**Thank you** to the VSD team and the entire open-source EDA community!

**Submitted by:** Kiran Kumar Siripurapu  
**Date:** 29 November 2025
