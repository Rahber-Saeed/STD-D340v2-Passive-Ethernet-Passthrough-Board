# STD-D340v2-Passive-Ethernet-Passthrough-Board
A passive industrial interface board designed to handle Telecom AC Mains Fail Alarm signals. It features triple RJ45 ports with full passive diode protection (MRA4004T3G) on critical lines, enabling reliable signal passthrough between PLC/PSU Alarm inputs, Non-Host devices, and Host systems.
# 🔌 Industrial Ethernet/Alarm Pass-through & Isolator Board (STD-D340v2.0)

This repository contains the complete hardware design for a rugged industrial PCB built to handle **Telecom AC Mains Fail Alarm** signals. 

The board provides a secure and reliable way to route signals between an **Alarm Source/PLC**, a **Non-Host device**, and a **Host System**. By incorporating protection diodes on signal lines 1-4, it helps prevent electrical backflow and potential damage to connected equipment, making it an ideal component for SCADA systems, Industrial Automation, and Telecom infrastructure.

> **Note:** This is a passive protection/interface PCB. It does not require external power.

---

## ✨ Key Features

*   **3x RJ45 Ports:** 
    *   `PLC/PSU_ALM_IN`: Input for alarm signals.
    *   `NON-HOST`: Intermediate stage control/interface connector.
    *   `HOST_PASSTHRU`: Final output to the host system.
*   **Signal Protection:** Four high-quality MRA4004T3G (400V, 1A) rectifier diodes on pins 1-4, providing robust isolation against voltage spikes and reverse currents.
*   **Direct Pass-through:** Pins 5-8 are directly connected between all three ports for seamless signal continuity.
*   **Industrial Grade Design:** Provides a clean, reliable physical layer for critical alarm/fault monitoring systems.
*   **Compact Form Factor:** Easily mounted on DIN rails (if enclosure supports it) or directly near PLCs and Telecom cabinets.

---

## 🖼️ Gallery
<img width="850" height="301" alt="Schematic_Ethernet_Based_PCB_Desiging_2026-05-02" src="https://github.com/user-attachments/assets/360b33b7-f3f7-4d0d-b982-8e37aaeb115b" />

| PCB Layout | Schematic |
<img width="778" height="490" alt="Ethernet_Based_PCB_Desiging_3D_Top_View" src="https://github.com/user-attachments/assets/52db314a-582e-4e0b-a57b-106247f1cacb" />

| :---: | :---: |
<img width="787" height="512" alt="Ethernet_Based_PCB_Desiging_3D_Bottom_View" src="https://github.com/user-attachments/assets/de1f81cf-4da5-4016-ae25-cde7f444c532" />

| [![PCB Top View](images/PCB_Top.png)](images/PCB_Top.png) | [![Schematic](images/Schematic.png)](images/Schematic.png) |
<img width="682" height="432" alt="Ethernet_Based_PCB_Desiging_2D_View" src="https://github.com/user-attachments/assets/eff69c34-35c6-42a3-b0df-16545b7714ac" />

---

## 🔌 Pinout & Signal Flow

The board acts as a straight passthrough with protection on the first four lines.

| Signal Line | Direction | Connector Relation | Protection |
| :--- | :--- | :--- | :--- |
| **Pins 1-4** | In/Out via Protection Diode | `PLC/PSU_ALM_IN` ⇢ `D1-D4` ⇢ `NON-HOST` ⇢ `HOST_PASSTHRU` | **Yes** (MRA4004T3G) |
| **Pins 5-8** | Direct Pass-through | `PLC/PSU_ALM_IN` ⇢ `NON-HOST` ⇢ `HOST_PASSTHRU` | **No** |

---

## 📦 Bill of Materials (BOM)

The complete BOM is available in the file [`BOM_Ethernet_Based_PCB_Desiging_2026-05-02.csv`](BOM_Ethernet_Based_PCB_Desiging_2026-05-02.csv).

| Component | Designator | Quantity | Description |
| :--- | :--- | :--- | :--- |
| **RJ45 Connectors** | PLC/PSU_ALM_IN, NON-HOST, HOST_PASSTHRU | 3 | `HC-RJ45-055-6` – 8-pin, SMD |
| **Rectifier Diode** | D1, D2, D3, D4 | 4 | `MRA4004T3G` – 400V, 1A |
| **PCB** | - | 1 | `STD-D340v2.0` (Standard 3-Port Interface Board) |

---

## 🔧 Hardware Usage

1.  **Assembly:** Solder all SMD components onto the PCB using the PickAndPlace file and BOM.
2.  **Integration:**
    *   Connect your **PLC/PSU** alarm output to the `PLC/PSU_ALM_IN` port using a standard Ethernet cable.
    *   Connect your **Host** (e.g., Central Monitoring System) to the `HOST_PASSTHRU` port.
    *   The `NON-HOST` port can be used for tapping or connecting intermediate devices.
3.  **Testing:** Apply your alarm signal (e.g., an AC Mains Fail voltage). Check continuity across protected lines (1-4) and direct lines (5-8) using a multimeter.

---

## 🗂️ Repository Structure
