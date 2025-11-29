# Digital VLSI SoC Design and Planning – Final Project Report  
**Design Name:** `spm` (Small Processing Module)  
**Author:** Kiran Kumar Siripurapu  
**PDK:** Skywater 130nm (sky130A)  
**Flow:** OpenLane 2.0 (OpenLane) – Full RTL to GDSII  
**Environment:** GitHub Codespaces  

**Final Result: Signoff-clean GDSII with 0 DRC, Timing Met, CVC Passed**

---

## Project Overview
This project demonstrates a complete **open-source ASIC physical design flow** from RTL → GDSII using **OpenLane** on the **Sky130A** PDK.  
The design `spm` (a simple processing module with custom ALU) was taken through synthesis, floorplanning, placement, CTS, routing, and full signoff verification — all inside GitHub Codespaces.

### Key Achievements
- Full OpenLane flow completed successfully  
- Final layout: **0 DRC errors** (Magic)  
- **Setup & Hold timing met** (OpenSTA)  
- **CVC passed** (netlist vs layout connectivity)  
- Final tapeout-ready GDSII generated  

---

## Design Summary

| Attribute              | Value                                      |
|-----------------------|--------------------------------------------|
| Design Name           | `spm` (Small Processing Module)            |
| Top Module            | `spm`                                      |
| RTL Source            | [`submission/RTL/spm.v`](submission/RTL/spm.v) |
| Technology            | Skywater 130nm (sky130A)                   |
| Tool Flow             | OpenLane 2 (OpenROAD)                      |
| Environment           | GitHub Codespaces                          |
| Final GDSII           | [`spm.gds`](submission/OpenLane/gds/spm.gds) |
|


---

## OpenLane Flow Summary

| Stage                   | Status | Remarks                              |
|-------------------------|--------|--------------------------------------|
| Synthesis (Yosys)       | Pass   | Gate-level netlist generated         |
| Floorplanning           | Pass   | PDN, IO pins, tap/decap inserted     |
| Placement               | Pass   | No congestion                        |
| Clock Tree Synthesis    | Pass   | Balanced clock tree                  |
| Routing (TritonRoute)   | Pass   | Global + detailed routing complete   |
| Parasitic Extraction    | Pass   | SPEF generated                       |
| **Final Signoff**       |        |                                      |
| DRC (Magic/KLayout)     | **0 errors** | Clean layout                     |
| STA (OpenSTA)           | **Met**     | Setup & hold slack positive          |
| CVC (Connectivity)      | **Passed**  | Layout matches netlist               |

---

## Layout Views (Magic)

| Description                          | Screenshot |
|--------------------------------------|---------|
| Full Chip Layout                     | ![Full Layout](submission/images/magic_layout_full.png) |
| Zoomed-out View                      | ![Full Zoom](submission/images/magic_layout_full_zoom.png) |
| Standard Cell Close-up               | ![Cell Zoom](submission/images/magic_layout_zoom.png) |
| Custom ALU Block (zoomed out)        | ![Custom ALU](submission/images/Custom%20ALU%20layout%20(zoomed-out%20view).png) |
| Magic + Extraction Log Side-by-Side  | ![Extraction + Layout](submission/images/Extraction%20log%20+%20simple_alu%20layout%20(Magic%20side-by-side).png) |
| Magic Console – Loading Design       | ![Loading](submission/images/Magic%20console%20loading%20ALU%20+%20initial%20load.png) |
| Magic DRC Check (0 errors)           | ![DRC Clean](submission/images/tkcon_drc_check.png) |

---

## Final Signoff Verification

### 1. DRC – Design Rule Check (Magic)
- **Result:** `0 violations`
- Report: [`drc.rpt`](submission/OpenLane/reports/signoff/drc.rpt)
- Screenshot: ![DRC 0](submission/images/tkcon_drc_check.png)

### 2. STA – Static Timing Analysis (OpenSTA)
- **Setup Slack:** Positive (met)
- **Hold Slack:** Positive (met)
- Key Reports:
  - [`31-rcx_sta.summary.rpt`](submission/OpenLane/reports/signoff/31-rcx_sta.summary.rpt)
  - [`31-rcx_sta.max.rpt`](submission/OpenLane/reports/signoff/31-rcx_sta.max.rpt)
  - [`31-rcx_sta.min.rpt`](submission/OpenLane/reports/signoff/31-rcx_sta.min.rpt)
- Terminal Output: ![STA Slack](submission/images/sta_summary_terminal-slack.png)

### 3. CVC – Circuit Validity Check
- **Result:** Passed – layout netlist matches synthesized netlist
- Report: [`spm.rpt`](submission/OpenLane/reports/signoff/spm.rpt)
- Screenshot: ![CVC Pass](submission/images/cvc_report.png)

---

## Key Output Files

| File Type     | Path                                                                 |
|---------------|----------------------------------------------------------------------|
| Final GDSII   | [`submission/OpenLane/gds/spm.gds`](submission/OpenLane/gds/spm.gds)  |
| Final DEF     | [`submission/OpenLane/def/spm.def`](submission/OpenLane/def/spm.def)  |
| RTL           | [`submission/RTL/spm.v`](submission/RTL/spm.v)                        |

### All Important Reports (Clickable)
#### Synthesis Reports
- [Area Report](submission/Synthesis/1-synthesis.AREA_0.stat.rpt)
- [Timing Summary](submission/Synthesis/2-syn_sta.summary.rpt)

#### Post-Route Signoff Reports
| Report                        | Link                                                                                   |
|-------------------------------|----------------------------------------------------------------------------------------|
| STA Summary                   | [31-rcx_sta.summary.rpt](submission/OpenLane/reports/signoff/31-rcx_sta.summary.rpt)   |
| STA Setup                     | [31-rcx_sta.max.rpt](submission/OpenLane/reports/signoff/31-rcx_sta.max.rpt)           |
| STA Hold                      | [31-rcx_sta.min.rpt](submission/OpenLane/reports/signoff/31-rcx_sta.min.rpt)           |
| DRC Report                    | [drc.rpt](submission/OpenLane/reports/signoff/drc.rpt)                                 |
| CVC Report                    | [spm.rpt](submission/OpenLane/reports/signoff/spm.rpt)                              |
| IR Drop (VPWR)                | [32-irdrop-VPWR.rpt](submission/OpenLane/reports/signoff/32-irdrop-VPWR.rpt)           |

---

## Folder Structure
