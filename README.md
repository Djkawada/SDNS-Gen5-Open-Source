# Secure NVMe Boot Selector (SDNS) - Open Source PCIe Gen 5.0 Project 🚀

The SDNS project aims to create the world's first **fully isolated, purely hardware-based** boot selector for multiple M.2 NVMe SSDs, operating at full **PCIe Gen 5.0 x4** speed.

This project offers the ultimate solution for multi-boot security by electrically isolating inactive operating systems, eliminating the risk of cross-corruption and software bootloader dependency.

---

## 🔍 Core Challenge

The non-negotiable requirement of **PCIe Gen 5.0 (32 GT/s)** across a cabled connection ($\approx 30 \text{ cm}$) makes this an **advanced Signal Integrity (SI)** challenge. The core design relies on successful implementation of **Retimer** and **MUX** circuitry to maintain speed and stability.

---

## 🛠️ Project Documentation and Contribution

All project requirements, architectural definitions, and critical component roles are detailed in the official project manifesto.

### [**➡️ READ THE FULL TECHNICAL MANIFESTO HERE**](01_Documentation/SDNS_Technical_Manifesto_v1.0.md)

### 🤝 We Need Your Expertise!

We are actively seeking experts in:

* **Signal Integrity / PCB Design** (Gen 5.0 Routing and Component Selection)
* **Embedded Firmware** (Secured Switching Sequence Logic)
* **Mechanical Design** (Enclosure and Selector Interface)

---

## Licensing

* Code: [MIT License](LICENSE_CODE.md)
* Hardware: [CERN Open Hardware Licence (OHL)](LICENSE_HARDWARE.md)

**Let's build the future of secure high-performance computing together!**
