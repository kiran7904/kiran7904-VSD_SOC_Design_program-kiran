# Digital VLSI SoC Design and Planning – Final Project Report

**Design Name:** `spm` (Small Processing Module)  
**Author:** Kiran Kumar Siripurapu  
**PDK:** Skywater 130nm (sky130A)  
**Flow:** OpenLane 2 – Full RTL → GDSII  
**Environment:** GitHub Codespaces  

**Final Result: 0 DRC | Timing Met | CVC Passed | Tapeout-Ready GDSII**

---

## Project Overview
Complete open-source ASIC implementation of the `spm` design using the **OpenLane** flow on **Sky130A** PDK.  
All stages from synthesis to signoff were executed successfully inside GitHub Codespaces.

### Key Achievements
- Full RTL-to-GDSII flow completed
- **DRC Clean** (0 errors – Magic)
- **Timing Closed** (Setup & Hold met – OpenSTA)
- **CVC Passed** (Layout vs Netlist match)
- Final GDSII & DEF generated

---

## Design Summary

| Attribute           | Value                                           |
|---------------------|-------------------------------------------------|
| Design Name         | `spm`                                           |
| RTL Source          | [`submission/RTL/spm.v`](submission/RTL/spm.v)  |
| Technology          | Sky130A (Skywater 130 nm)                       |
| Tool Flow           | OpenLane 2                                      |
| Final GDSII         | [`spm.gds`](submission/OpenLane/gds/spm.gds)    |
| Final DEF           | [`spm.def`](submission/OpenLane/def/spm.def)    |

---

## OpenLane Flow Status

| Stage                  | Status | Remarks                          |
|------------------------|--------|----------------------------------|
| Synthesis              | Pass   | Yosys netlist generated          |
| Floorplan              | Pass   | PDN + IO + tap/decap             |
| Placement              | Pass   | No congestion                    |
| CTS                    | Pass   | Balanced clock tree              |
| Routing                | Pass   | TritonRoute complete             |
| DRC (Magic)            | **0 errors** | Clean                        |
| STA (OpenSTA)          | **Met**     | Positive slack               |
| CVC                    | **Passed**  | Netlist matches layout       |

---

## Layout & Verification Screenshots

| Description                                    | Image |
|------------------------------------------------|-------|
| Complete LibreLane Scan                        | ![Complete LibreLane Scan](submission/images/Complete_librelane_scan.jpg) |
| Custom ALU Layout (zoomed-out view)            | ![Custom ALU](submission/images/Custom%20ALU%20layout%20(zoomed-out%20view).png) |
| Extraction Log + simple_alu layout (side-by-side) | ![Extraction + ALU](submission/images/Extraction%20log%20+%20simple_alu%20layout%20(Magic%20side-by-side).png) |
| OpenLane Run Reports Directory                 | ![Reports Dir](submission/images/OpenLane%20run%20reports%20directory%20view.png) |
| Full Chip Layout (Magic)                       | ![Full Layout](submission/images/magic_layout_full.png) |
| Full Layout – Zoomed Out                       | ![Full Zoom](submission/images/magic_layout_full_zoom.png) |
| Standard Cell Close-Up                         | ![Cell Zoom](submission/images/magic_layout_zoom.png) |
| Reports Directory View                         | ![Reports](submission/images/reports_directory.png) |
| Signoff Reports Folder                         | ![Signoff](submission/images/signoff_reports.png) |
| STA Summary File                               | ![STA File](submission/images/sta_summary_file.png) |
| STA Terminal Slack (Positive)                  | ![STA Slack](submission/images/sta_summary_terminal-slack.png) |
| Magic DRC Check → 0 Errors                     | ![DRC Clean](submission/images/tkcon_drc_check.png) |
| Final Zero DRC Confirmation                    | ![Zero DRC](submission/images/zero_drc.png) |
| CVC Report – Passed                            | ![CVC](submission/images/cvc_report.png) |

---

## Final Signoff Results

### DRC (Magic/KLayout)
- **0 violations**
- Report → [`drc.rpt`](submission/OpenLane/reports/signoff/drc.rpt)

### STA (OpenSTA – Post-Route RCX)
- Setup & Hold slack **positive**
- Key reports:
  - [`31-rcx_sta.summary.rpt`](submission/OpenLane/reports/signoff/31-rcx_sta.summary.rpt)
  - [`31-rcx_sta.max.rpt`](submission/OpenLane/reports/signoff/31-rcx_sta.max.rpt)
  - [`31-rcx_sta.min.rpt`](submission/OpenLane/reports/signoff/31-rcx_sta.min.rpt)

### CVC (Connectivity Verification)
- **Passed** – No mismatches
- Report → [`spm.rpt`](submission/OpenLane/reports/signoff/spm.rpt)

---

## Important Files (Clickable Links)

### Core Deliverables
| File            | Link                                                                 |
|-----------------|----------------------------------------------------------------------|
| Final GDSII     | [spm.gds](submission/OpenLane/gds/spm.gds)                           |
| Final DEF       | [spm.def](submission/OpenLane/def/spm.def)                           |
| RTL Source      | [spm.v](submission/RTL/spm.v)                                        |

### Signoff Reports
| Report                    | Link                                                                                   |
|---------------------------|----------------------------------------------------------------------------------------|
| DRC Report                | [drc.rpt](submission/OpenLane/reports/signoff/drc.rpt)                                 |
| STA Summary               | [31-rcx_sta.summary.rpt](submission/OpenLane/reports/signoff/31-rcx_sta.summary.rpt)   |
| STA Setup                 | [31-rcx_sta.max.rpt](submission/OpenLane/reports/signoff/31-rcx_sta.max.rpt)           |
| STA Hold                  | [31-rcx_sta.min.rpt](submission/OpenLane/reports/signoff/31-rcx_sta.min.rpt)           |
| CVC Report                | [spm.rpt](submission/OpenLane/reports/signoff/spm.rpt)                                 |
| IR Drop (VPWR)            | [32-irdrop-VPWR.rpt](submission/OpenLane/reports/signoff/32-irdrop-VPWR.rpt)           |

### Synthesis Reports
| Report                    | Link                                                                      |
|---------------------------|---------------------------------------------------------------------------|
| Area Report               | [1-synthesis.AREA_0.stat.rpt](submission/Synthesis/1-synthesis.AREA_0.stat.rpt) |
| Synthesis Timing Summary  | [2-syn_sta.summary.rpt](submission/Synthesis/2-syn_sta.summary.rpt)       |

---

## Folder Structure
