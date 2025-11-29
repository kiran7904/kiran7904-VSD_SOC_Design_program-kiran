# 💾 Digital VLSI SoC Design and Planning – Final Project Report
## ⚙ Design Details
| Attribute       | Value                        |
|-----------------|------------------------------|
| *Design Name*   | `spm` (Small Processing Module) |
| *Author*        | Kiran Kumar Siripurapu       |
| *PDK*           | Sky130A (Open-Source)        |
| *Flow Used*     | OpenLane (RTL → GDSII)       |
| *Environment*   | GitHub Codespaces            |

---

## 📘 Project Overview
This project successfully implemented the **spm** (small processing module) design using the *OpenLane RTL-to-GDSII flow* on the *Sky130A PDK*. The goal was to complete a full ASIC physical design flow, resulting in a signoff-clean **GDSII layout**. The entire process was executed in GitHub Codespaces, yielding a functionally and physically verified design.

### 🎯 Key Deliverables
- RTL (`spm.v`)
- Synthesis Reports (Area, Timing)
- OpenLane Logs & Results
- Final GDSII & DEF Files
- *Signoff:* DRC, STA, CVC Verification

---

## 1. 🧩 RTL Design
| Explanation                                      | File / View                                      |
|--------------------------------------------------|--------------------------------------------------|
| Original Verilog RTL used without modification   | [submission/RTL/spm.v](submission/RTL/spm.v)     |

---

## 2. 🚀 OpenLane Flow Summary
The RTL-to-GDSII flow was completed successfully with no fatal errors, passing all signoff checks.

| OpenLane Stage          | Status    | Details                          |
|--------------------------|-----------|----------------------------------|
| *Synthesis*             | ✔ Done    | RTL to gate-level netlist (Yosys) |
| *Floorplan*             | ✔ Done    | Core boundary, IO, PDN generated  |
| *Placement*             | ✔ Done    | No congestion issues             |
| *Clock Tree Synthesis*  | ✔ Done    | Balanced clock tree              |
| *Routing*               | ✔ Done    | Global & detailed (TritonRoute)  |
| *GDSII Generation*      | ✔ Done    | Fabrication-ready layout         |
| *DRC (Magic)*           | *✔ 0 Errors* | Design Rule Check Passed         |
| *STA (OpenSTA)*         | *✔ Slack Met* | Setup & Hold Timing Passed       |
| *CVC (Netlist Check)*   | *✔ Passed* | Connectivity Verified            |

> All results and reports are in: `submission/OpenLane/`

---

## 3. 📝 Synthesis & Physical Design
### 3.1. Synthesis (Yosys)
| Explanation                                      | Output Location                                  |
|--------------------------------------------------|--------------------------------------------------|
| Generated netlist, area, and timing reports      | `submission/Synthesis/`                          |

### 3.2. Floorplan & Placement
| Explanation                                      | Details                                          |
|--------------------------------------------------|--------------------------------------------------|
| Included PDN, IO placement, tapcell, decap insertion | No congestion reported                          |

### 3.3. Clock Tree Synthesis (CTS)
| Explanation                                      | Reports Location                                 |
|--------------------------------------------------|--------------------------------------------------|
| Balanced clock tree inserted to meet timing      | `submission/OpenLane/reports/placement/` & `cts/` |

### 3.4. Routing
| Explanation                                      | Output Location                                  |
|--------------------------------------------------|--------------------------------------------------|
| Completed using FastRoute & TritonRoute, with SPEF | `submission/OpenLane/results/final/`             |

---

## 4. 🖼 Magic Layout Screenshots
| Explanation                                      | Image                                             |
|--------------------------------------------------|---------------------------------------------------|
| Full layout post-routing                         | ![Full Layout](submission/images/magic_layout_full.png) |
| Zoomed-out view of full layout                   | ![Full Zoom](submission/images/magic_layout_full_zoom.png) |
| Close-up of standard cells                       | ![Standard Cell Zoom](submission/images/magic_layout_zoom.png) |

---

## 5. ✅ Final Signoff Verification
### 5.1. 🧪 DRC (Design Rule Check)
| Explanation                                      | Screenshot / Report                              |
|--------------------------------------------------|--------------------------------------------------|
| Final DRC check on GDSII layout (0 errors)       | ![TKCON DRC Check](submission/images/tkcon_drc_check.png) |
| Initial DRC report with 144 errors (resolved)    | ![Initial DRC 144](submission/images/Magic%20console%20loading%20ALU%20+%20initial%20DRC%20report.png) |
| **Report Location:**                            | [drc.rpt](submission/OpenLane/reports/signoff/drc.rpt) |

### 5.2. ⏱ STA (Static Timing Analysis)
| Explanation                                      | Screenshot / Report                              |
|--------------------------------------------------|--------------------------------------------------|
| Verified timing constraints (Setup & Hold met)   | ![STA Slack Terminal](submission/images/sta_summary_terminal-slack.png) |
| **Reports Location:**                           | `submission/OpenLane/reports/signoff/`            |
| STA Summary Report                               | [31-rcx_sta.summary.rpt](submission/OpenLane/reports/signoff/31-rcx_sta.summary.rpt) |

### 5.3. 🧬 CVC (Connectivity Verification)
| Explanation                                      | Screenshot / Report                              |
|--------------------------------------------------|--------------------------------------------------|
| Verified layout netlist vs synthesized netlist   | ![CVC Report](submission/images/cvc_report.png)  |
| **Report Location:**                            | [spm.rpt](submission/OpenLane/reports/signoff/spm.rpt) |

---

## 6. 🧾 Final GDSII & DEF Files
| File Type          | Path                                              |
|--------------------|---------------------------------------------------|
| *GDSII File*       | [submission/OpenLane/gds/spm.gds](submission/OpenLane/gds/spm.gds) |
| *DEF File*         | [submission/OpenLane/def/spm.def](submission/OpenLane/def/spm.def) |

---

## 7. 🔗 Clickable Report & File Links
### 🔹 Core Layout Files
| File            | Link                                              |
|-----------------|---------------------------------------------------|
| *Final GDSII*   | [submission/OpenLane/gds/spm.gds](submission/OpenLane/gds/spm.gds) |
| *Final DEF*     | [submission/OpenLane/def/spm.def](submission/OpenLane/def/spm.def) |
| *RTL Source*    | [submission/RTL/spm.v](submission/RTL/spm.v)      |

### 🔹 Signoff Reports
| Report Type      | File            | Link                                              |
|------------------|-----------------|---------------------------------------------------|
| *DRC Report*     | `drc.rpt`       | [drc.rpt](submission/OpenLane/reports/signoff/drc.rpt) |
| *STA Summary*    | `31-rcx_sta.summary.rpt` | [31-rcx_sta.summary.rpt](submission/OpenLane/reports/signoff/31-rcx_sta.summary.rpt) |
| *STA Max*        | `31-rcx_sta.max.rpt` | [31-rcx_sta.max.rpt](submission/OpenLane/reports/signoff/31-rcx_sta.max.rpt) |
| *STA Min*        | `31-rcx_sta.min.rpt` | [31-rcx_sta.min.rpt](submission/OpenLane/reports/signoff/31-rcx_sta.min.rpt) |
| *CVC Report*     | `spm.rpt`       | [spm.rpt](submission/OpenLane/reports/signoff/spm.rpt) |
| *IR Drop*        | `32-irdrop-VPWR.rpt` | [32-irdrop-VPWR.rpt](submission/OpenLane/reports/signoff/32-irdrop-VPWR.rpt) |

### 🔹 Synthesis Reports
| Report Type      | File            | Link                                              |
|------------------|-----------------|---------------------------------------------------|
| *Area Report*    | `1-synthesis.AREA_0.stat.rpt` | [1-synthesis.AREA_0.stat.rpt](submission/Synthesis/1-synthesis.AREA_0.stat.rpt) |
| *STA Summary*    | `2-syn_sta.summary.rpt` | [2-syn_sta.summary.rpt](submission/Synthesis/2-syn_sta.summary.rpt) |
| *SDF File*       | `spm.sdf`       | [spm.sdf](submission/Synthesis/spm.sdf)           |

---

## 8. 📦 Submission Folder Structure
