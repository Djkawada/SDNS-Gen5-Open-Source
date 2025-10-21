Secure NVMe Boot Selector (SDNS) - Open Source PCIe Gen 5.0 Project 🚀
The SDNS project aims to create the world's first fully isolated, purely hardware-based boot selector for multiple M.2 NVMe SSDs, operating at full PCIe Gen 5.0 speeds.

1. Vision & Problem Statement
The Problem
Modern multi-boot setups rely on software bootloaders (like GRUB or Windows Boot Manager) which introduce risk:

Risk of Corruption: Operating systems can see and potentially modify the boot partitions or data of other OS installations.

Speed Compromise: Many existing multi-drive adapters rely on complex BIOS bifurcation settings or slower bus protocols.

Our Solution: Absolute Hardware Isolation
The SDNS system guarantees that only one single SSD is electrically connected and logically visible to the host system (the BIOS/UEFI) at any given time. This completely bypasses software conflicts and ensures the inactive OS installations are protected at the deepest hardware level.

2. Non-Negotiable Core RequirementsThis is a high-risk, high-reward project.
The technical complexity stems directly from the speed requirement.
Core Objectives:
Performance Absolute: PCIe Gen 5.0 x4 (32 GT/s) on the active SSD. This guarantees maximum speed (up to $\approx 15.75 \text{ GB/s}$).
Isolation Maximal: Full Electrical Cutoff. Power ($\mathbf{3.3V}$) and all secondary signals must be switched off for inactive drives. This ensures absolute data integrity.
Capacity: Initial target: Support for 4 M.2 NVMe SSDs (4:1 selector).
Interface: Physical, mechanical selector switch, designed for desktop integration.
Safety Protocol: Switching must only be possible when the host PC is confirmed to be powered OFF.

3. Technical Architecture & Design Challenges

The SDNS is composed of three interconnected modules. The central challenge is Signal Integrity (SI) at 32 GT/s across the cable assembly.
A. Modular BreakdownHost 
  Adapter PCB: Plugs into the motherboard's M.2 slot. Primary role is to connect the PCIe lanes to the high-speed cable assembly. Must include space for the Retimer chip.
  Gen 5.0 Interconnect Cable: Short, specialized cable ($\mathbf{< 30 \text{ cm}}$ twinaxial or FFC) to minimize signal loss.
  Main Selector Enclosure: The core unit. This houses the 4 M.2 slots, the switching logic, and the power management circuits. This unit is designed to fit within a standard PC $\mathbf{2.5" / 3.5"}$ drive bay.
B. Critical Component Selection
  We need expert help to finalize the specific part numbers for these components:
  1. PCIe Gen 5.0 Retimer
     Critical Function: Regenerates the signal to compensate for the significant loss introduced by the cable and connectors.
     Technical Challenge: Must participate correctly in the PCIe Link Training protocol at 32 GT/s. Requires Ingénierie Signal Integrity (SI) for chip selection and placement.
  2. PCIe MUX/DEMUX 4:1
     Critical Function: Switches the four $x4$ PCIe lanes from the Retimer output to the selected M.2 drive.
     Technical Challenge: Requires extremely low insertion loss and excellent crosstalk performance at Gen 5.0 frequencies.
  3. Microcontroller (MCU)
     Critical Function: Executes the Secured Switching Sequence (SSS): Verify Power-Off, Cut Power, Switch MUX, Power ON.
     Technical Challenge: Requires low-latency firmware programming to ensure critical timing.
  4. Power Management (MOSFETs/Load Switches)
     Critical Function: Cuts the $\mathbf{3.3V}$ power line to the inactive SSDs.
     Technical Challenge: Must handle the SSD's high current draw while ensuring rapid and safe cutoff/startup sequencing.

4. Collaboration & Next Steps
This project is open-source because its complexity demands collective expertise.

Expertise We Need:
Signal Integrity / PCB Design: Experts in PCIe Gen 5.0 routing, MUX/Retimer implementation, and low-loss materials.

Embedded Firmware: C/C++ developers experienced with MCU control logic and low-level hardware sequencing.

Mechanical Design: 3D modelers for the functional enclosure and the external selector knob design.

Project Status and Milestones
Current Phase: Architectural Definition Complete.

Next Major Milestone: Proof-of-Concept Schematic and BOM (Bill of Materials) Validation.

Financial Strategy
Due to the high cost of components and specialized PCB fabrication, this project will rely on Crowdfunding to finance the initial professional fabrication runs. 
All funds raised will be dedicated exclusively to producing the hardware and paying for necessary professional testing (like PCIe Compliance Testing).

Licensing
Code: MIT License
Hardware (Schematics/Layout): CERN Open Hardware Licence (OHL)

Repository Maintainer: Djkawada 
Contact: pierre.jap@gmail.com
