# Digital VLSI SoC Design and Planning – Final Project Report  
## **Design Name:** `spm`  
## **Author:** Kiran kumar siripurapu 
## **PDK:** Sky130A  
## **Flow Used:** OpenLane (RTL → GDSII)**

---

## 📘 Overview

This project implements the `spm` (small processing module) design using the OpenLane RTL-to-GDSII flow on the Sky130A open-source PDK.  
The goal was to take the given RTL and harden it into a complete ASIC layout, ending with a clean GDSII.

This report includes:
- RTL  
- Synthesis results  
- OpenLane logs  
- Magic screenshots  
- DRC, STA, CVC results  
- Final GDS & DEF  

The entire flow was completed inside GitHub Codespaces.
## 📘 Overview

This project implements the **`spm`** (small processing module) design using the **OpenLane RTL-to-GDSII flow** on the **Sky130A open-source PDK**.  
The objective was to perform a full ASIC physical design flow and generate a signoff-clean **GDSII layout**.

The project includes all required deliverables:
- RTL  
- Synthesis reports  
- OpenLane logs & results  
- GDSII & DEF  
- DRC, STA, and CVC signoff  
- Magic screenshots  
- Complete physical verification  

---
# 🧩 1. RTL Design

The RTL file used:

`/home/vscode/Desktop/OpenLane/designs/spm/submission/RTL/spm.v`


No RTL modifications were required for this project.
# ⚙️ 2. Synthesis (Yosys)

Synthesis was completed successfully using Yosys inside the OpenLane flow.

The synthesis stage generated:
- Synthesized netlist  
- Area reports  
- Timing reports  
- SDF (Standard Delay Format)  
- Cell usage statistics  

All synthesis outputs are stored in:  `submission/Synthesis/`


The synthesis stage completed successfully and produced:
- Synthesized netlist  
- Area and timing reports  
- SDF (Standard Delay Format)

# 🧱 3. OpenLane Flow Summary

The entire OpenLane RTL-to-GDSII flow was successfully executed for the `spm` design.
Each stage completed without fatal errors, and final signoff checks passed.

### ✔ Flow Stages Completed

| OpenLane Stage | Status |
|----------------|--------|
| Synthesis | ✔ Done |
| Floorplan | ✔ Done |
| Placement | ✔ Done |
| Clock Tree Synthesis (CTS) | ✔ Done |
| Routing | ✔ Done |
| GDSII Generation | ✔ Done |
| DRC (Magic) | ✔ 0 Errors |
| STA (OpenSTA) | ✔ Slack Met |
| CVC (Connectivity Check) | ✔ Passed |

All OpenLane-generated files (DEF, GDS, results, reports, logs) are stored under:`submission/OpenLane/`

# 🗺️ 4. Floorplan

The floorplan stage automatically generated:

- Core boundary  
- IO pin placement  
- Power Distribution Network (PDN)  
- Standard cell rows  
- Tapcells and decap insertion  

Floorplan reports are available in:

`submission/OpenLane/reports/floorplan/`
# ⚙️ 5. Placement & Clock Tree Synthesis (CTS)

The placement stage completed successfully with no congestion issues.  
Standard cells were placed and legalized across the floorplan.

Clock Tree Synthesis (CTS) inserted buffers and generated a balanced clock tree for timing closure.

All related reports are stored in:

- `submission/OpenLane/reports/placement/`
- `submission/OpenLane/reports/cts/`
# 🔧 6. Routing

Routing was completed using FastRoute and TritonRoute.  
The final routed DEF, parasitic extraction files, and timing data were generated successfully.

Final routing-related outputs are available in:

`submission/OpenLane/results/final/`
# 🖼️ 7. Magic Layout Screenshots

![Full Layout](submission/images/magic_layout_full.png)

![Full Zoom](submission/images/magic_layout_full_zoom.png)

![Standard Cell Zoom](submission/images/magic_layout_zoom.png)

![Magic DRC Menu](submission/images/magic_drc_menu.png)

![TKCON DRC Check](submission/images/tkcon_drc_check.png)




# 🧪 8. DRC (Design Rule Check)

Magic DRC was performed on the final layout.

**Final Result:**  
**Total DRC errors = 0**

![DRC Reports](submission/images/reports_directory.png)


All DRC reports are stored in:

`submission/Physical_Verification/`
# 🧬 9. CVC (Connectivity Verification Check)

CVC (Circuit Validity Checker) was run on the final extracted layout.  
It checks for:

- Shorts  
- Opens  
- Floating nodes  
- Incorrect connections  
- Power/ground issues  

**CVC passed successfully.**

### CVC Screenshot
![CVC Report](submission/images/cvc_report.png)


Static Timing Analysis was performed on the final routed design.

Both **setup** and **hold** timing checks were MET.

### STA Slack Terminal
![STA Summary File](submission/images/sta_summary_file.png)

![STA Slack Terminal](submission/images/sta_summary_terminal-slack.png)


# 🗂️ 11. Final Signoff Reports

The final signoff stage generated all required verification outputs, including:

- DRC reports  
- CVC reports  
- STA reports  
- SPEF (parasitics)  
- SDF  
- Extraction feedback  
- Additional OpenLane multi-corner analysis (mca) folders  

### Signoff Reports
![Signoff Reports![Signoff Reports](submission/images/signoff_reports.png)



All signoff outputs are stored in:

`submission/Physical_Verification/`
# 🧾 12. Final GDS & DEF

The final fabrication-ready layout files are included in the submission.

### GDSII File:
`submission/OpenLane/gds/spm.gds`

### DEF File:
`submission/OpenLane/def/spm.def`

These files represent the final placed, clocked, and routed physical layout of the `spm` design.

# 📦 13. Submission Folder Structure

The final submission follows the recommended VSD folder format:

```
submission/
│── RTL/
│   └── spm.v
│
│── Synthesis/
│   ├── 1-synthesis.AREA_0.stat.rpt
│   ├── 1-synthesis.AREA_0.chk.rpt
│   ├── ...
│
│── OpenLane/
│   ├── gds/
│   │   └── spm.gds
│   ├── def/
│   │   └── spm.def
│   ├── results/
│   ├── reports/
│   │   └── signoff/
│   ├── logs/
│   ├── images/
│       ├── magic_layout_full.png
│       ├── magic_layout_full_zoom.png
│       ├── magic_layout_zoom.png
│       ├── magic_drc_menu.png
│       ├── tkcon_drc_check.png
│       ├── reports_directory.png
│       ├── sta_summary_terminal-slack.png
│       ├── sta_summary_file.png
│       ├── signoff_reports.png
│       └── cvc_report.png
│
│── Physical_Verification/
│   ├── drc reports
│   ├── sta reports
│   ├── cvc reports
│
└── README.md



# 🏁 Conclusion

The `spm` design was successfully implemented from RTL to GDSII using the OpenLane flow on the Sky130A PDK.

All major signoff checks passed:
- ✔ DRC: 0 errors  
- ✔ STA: Setup and Hold MET  
- ✔ CVC: Passed  

The final design is fully routed, timing-clean, and ready for fabrication.  
This submission includes all required project artifacts — GDS, DEF, reports, logs, and verification screenshots.

---

# 📎 14. Clickable Report & File Links (GitHub Compatible)

Below are direct links to all major reports and output files for easy navigation.

---

## 🔹 Synthesis Reports  
(Located in: `submission/Synthesis/`)

- [Area Report](submission/Synthesis/1-synthesis.AREA_0.stat.rpt)
- [Area Check Report](submission/Synthesis/1-synthesis.AREA_0.chk.rpt)
- [DFF Report](submission/Synthesis/1-synthesis_dff.stat)
- [Pre-synthesis Report](submission/Synthesis/1-synthesis_pre.stat)
- [Pre-synthesis Check](submission/Synthesis/1-synthesis_pre_synth.chk.rpt)
- [STA Checks](submission/Synthesis/2-syn_sta.checks.rpt)
- [STA Max](submission/Synthesis/2-syn_sta.max.rpt)
- [STA Min](submission/Synthesis/2-syn_sta.min.rpt)
- [STA Power](submission/Synthesis/2-syn_sta.power.rpt)
- [STA Skew](submission/Synthesis/2-syn_sta.skew.rpt)
- [STA Summary](submission/Synthesis/2-syn_sta.summary.rpt)
- [SDF File](submission/Synthesis/spm.sdf)

---

## 🔹 Signoff Reports (Post-Route)
(Located in: `submission/OpenLane/reports/signoff/`)

### STA (OpenSTA)
- [STA Checks](submission/OpenLane/reports/signoff/31-rcx_sta.checks.rpt)
- [STA Max](submission/OpenLane/reports/signoff/31-rcx_sta.max.rpt)
- [STA Min](submission/OpenLane/reports/signoff/31-rcx_sta.min.rpt)
- [STA Power](submission/OpenLane/reports/signoff/31-rcx_sta.power.rpt)
- [STA Skew](submission/OpenLane/reports/signoff/31-rcx_sta.skew.rpt)
- [STA Summary](submission/OpenLane/reports/signoff/31-rcx_sta.summary.rpt)

### DRC (Magic)
- [DRC Report](submission/OpenLane/reports/signoff/drc.rpt)
- [DRC TCL Script](submission/OpenLane/reports/signoff/drc.tcl)
- [DRC Raw Data (rdb)](submission/OpenLane/reports/signoff/drc.rdb)
- [DRC KLayout XML](submission/OpenLane/reports/signoff/drc.klayout.xml)
- [DRC TR File](submission/OpenLane/reports/signoff/drc.tr)

### CVC (Connectivity)
- [CVC Report](submission/OpenLane/reports/signoff/spm.rpt)
- [CVC Debug Log](submission/OpenLane/reports/signoff/spm.rpt.debug.gz)
- [CVC Error Log](submission/OpenLane/reports/signoff/spm.rpt.error.gz)

### Additional Signoff
- [IR Drop VGND](submission/OpenLane/reports/signoff/32-irdrop-VGND.rpt)
- [IR Drop VPWR](submission/OpenLane/reports/signoff/32-irdrop-VPWR.rpt)
- [XOR Report](submission/OpenLane/reports/signoff/35-xor.rpt)
- [XOR XML](submission/OpenLane/reports/signoff/35-xor.xml)
- [SPICE Feedback](submission/OpenLane/reports/signoff/spice.feedback.txt)

---

## 🔹 Final GDS & DEF  
(Located in: `submission/OpenLane/gds/` and `submission/OpenLane/def/`)

- [GDSII File (spm.gds)](submission/OpenLane/gds/spm.gds)
- [DEF File (spm.def)](submission/OpenLane/def/spm.def)

---

## 🔹 Folder Shortcuts

- [Synthesis Folder](submission/Synthesis/)
- [Signoff Reports](submission/OpenLane/reports/signoff/)
- [GDS Folder](submission/OpenLane/gds/)
- [DEF Folder](submission/OpenLane/def/)
- [Physical Verification Folder](submission/Physical_Verification/)


# 🙌 Acknowledgement

Thanks to the VSD Open-Source team for providing training, tools, and guidance.

