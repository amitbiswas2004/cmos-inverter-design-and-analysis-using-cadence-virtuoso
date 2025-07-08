# 📘 CMOS Inverter Analysis using Cadence Virtuoso (GPDK 90nm)

This repository presents a detailed design and analysis of a basic **CMOS inverter** using the **Cadence Virtuoso** design suite with the **GPDK 090 (90nm Generic Process Design Kit)**. Simulations are performed in the **ADE L (Analog Design Environment)** using the **Spectre simulator**, with a focus on evaluating both **DC transfer characteristics** and **transient behavior**.

The primary objective is to analyze the operation of the most fundamental digital logic gate—the inverter—at the transistor level, and to extract key performance parameters that form the basis of digital integrated circuit design.

---

## 📚 Contents

### 🛠️ Tools Used
- **Cadence Virtuoso** – For schematic entry and layout design
- **GPDK 090** – 90nm Generic Process Design Kit for academic use
- **ADE L** – Analog Design Environment for circuit simulation
- **Spectre** – SPICE-based simulation engine integrated with Virtuoso

---

## 💡 Why CMOS Circuits?

CMOS (Complementary Metal-Oxide-Semiconductor) circuits are the backbone of digital electronics due to their:
- Low static power consumption
- High noise immunity
- Excellent scalability in deep submicron technologies

The **CMOS inverter** is the fundamental building block of digital ICs such as logic gates, flip-flops, memory cells, and processors. It combines the best characteristics of PMOS and NMOS transistors, using:
- A **pull-up network** formed by the PMOS
- A **pull-down network** formed by the NMOS

These transistors operate primarily as switches, alternating between **cutoff**, **linear**, and **saturation regions** based on input conditions, thus achieving the desired inverting behavior.

---

## 📈 DC and Transient Analysis

### 🔋 DC Analysis
- **Input Voltage Sweep:** 0 V to 1 V
- **Observed Parameter:** Voltage Transfer Characteristic (VTC)
- 

### ⚡ Transient Analysis
- **Input Source:** `vpulse`
- **Simulation Time:** 0 ns to 100 ns
- **Pulse Parameters:**
  - **Period:** 10 ns  
  - **Rise Time:** 50 ps  
  - **Fall Time:** 50 ps  
  - **V1 (Low):** 1 V  
  - **V2 (High):** 2 V

The transient response helps determine:
- Output waveform shape
- Rise and fall times
- Propagation delays

---

## 📷 Simulation Screenshots

### 🔧 Schematic

![CMOS Inverter Schematic](https://github.com/user-attachments/assets/7a9d41c8-8a86-47b2-9561-9d5e13e5f77a)

> *Figure 1: CMOS inverter schematic using GPDK090*

---

### 🔣 Symbol View

![CMOS Inverter Symbol](https://github.com/user-attachments/assets/3219abe1-84dd-4483-b614-2a6c767b0fc1)

> *Figure 2: Auto-generated symbol view of the inverter*

---

### ⏱️ Transient Analysis

![Transient Response](https://github.com/user-attachments/assets/2744029d-20c3-4966-aff0-c375f77efc42)

> *Figure 3: Output waveform showing the inverter's response to a periodic pulse input*

---

### 📉 DC Transfer Characteristic

![DC Response](https://github.com/user-attachments/assets/4d3e279c-ab32-43a9-9ac1-c365d0c6f82c)

> *Figure 4: Voltage Transfer Characteristic (VTC) curve obtained from DC analysis*

---

## 👨‍💻 Author

**Jhelum Pradhan**  
Electronics and Communication Enthusiast | Analog Design Learner  
*This repository is part of an academic exploration into the fundamentals of CMOS logic design.*

---

## 📄 License

This work is shared under the [MIT License](LICENSE) and intended for **educational and non-commercial use**.

---

