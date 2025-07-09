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

- ✅ Low static power consumption  
- ✅ High noise immunity  
- ✅ Excellent scalability in deep submicron technologies

The **CMOS inverter** is the fundamental building block of digital ICs such as logic gates, flip-flops, memory cells, and processors. It combines the best characteristics of PMOS and NMOS transistors using:

- A **pull-up network** (PMOS)  
- A **pull-down network** (NMOS)

These transistors operate as switches, alternating between **cutoff**, **linear**, and **saturation regions** based on input conditions, thus achieving the desired inverting behavior.

---

## 📈 DC and Transient Analysis

### 🔋 DC Analysis

- **Input Voltage Sweep:** 0 V to 1 V  
- **Observed Parameter:** Voltage Transfer Characteristic (VTC)  

### ⚡ Transient Analysis

- **Input Source:** `vpulse`  
- **Simulation Time:** 0 ns to 100 ns  
- **Pulse Parameters:**
  - **Period:** 10 ns  
  - **Rise Time:** 50 ps  
  - **Fall Time:** 50 ps  
  - **V1 (Low):** 0 V  
  - **V2 (High):** 1 V

The transient response helps determine:

- Output waveform shape  
- Rise and fall times  
- Propagation delays  

---

## 📷 Simulation Screenshots

### 🔧 Schematic

![Screenshot_20250709_130421](https://github.com/user-attachments/assets/73be2c7f-eb89-40cf-86a9-20fabb6134b2)

> *Figure 1: CMOS inverter schematic using GPDK090*

---

### 🔣 Symbol View

![cadence cmos inverter](https://github.com/user-attachments/assets/c33c6c93-1aa9-4964-bdac-e28862d3b43d)

> *Figure 2: Auto-generated symbol view of the inverter*

---

### ⏱️ Transient Response

![transient response output voltage](https://github.com/user-attachments/assets/0395db49-9705-4f76-b74c-0ff93e36f2a2)

> *Figure 3: Output waveform showing the inverter's response to a periodic pulse input*

---

## 🔬 DC Transfer Characteristic Analysis

The CMOS inverter was designed using **Cadence Virtuoso** with the **GPDK 90nm** process. Initially, both **NMOS and PMOS transistors** were sized with:

- **Width (W) = 120 nm**  
- **Length (L) = 120 nm**

This size represents the minimum feature dimension for this node.

A **DC transfer characteristic (VTC)** simulation was carried out using **ADE L**. However, the results showed that the **switching threshold** (where \( V_{\text{in}} = V_{\text{out}} \)) was **not centered at 0.5 V (i.e., V<sub>DD</sub>/2)**. Instead, it occurred at a **higher voltage**, indicating imbalance between PMOS and NMOS drive strengths. This leads to **asymmetrical noise margins**—undesirable in inverter design.

---

### ⚙️ Experimental Tuning of PMOS Width

To resolve the imbalance, we **varied the PMOS width (W<sub>p</sub>)**, while **keeping NMOS width fixed at 120 nm**. A **parametric sweep** of W<sub>p</sub> was performed from **100 nm to 20000 nm**, and the corresponding VTCs were analyzed.

> 📌 **Observation:** Increasing PMOS width shifted the switching threshold leftward, approaching **0.5 V**.

#### ✅ Key Result:

- At approximately **W<sub>p</sub> = 415 nm**, the inverter achieved a **balanced switching threshold** close to **0.5 V**.
- This resulted in a **symmetrical VTC**, with **improved noise margins** and proper drive matching.

---

### 📈 Supporting Plots and Results

#### 📊 PMOS Width Sweep and Corresponding VTCs

![Screenshot_20250709_125407](https://github.com/user-attachments/assets/3168ff27-f4d0-4d8c-b4d0-52cf0069b84b)

> *Figure 4: Multiple VTCs for different PMOS widths showing threshold shifts*

---

#### 📊 Final VTC with Optimized W<sub>p</sub>

![Screenshot_20250709_130935](https://github.com/user-attachments/assets/6f45ff70-cf70-4416-ac71-a646e1f0479c)

> *Figure 5: Final VTC for W<sub>p</sub> = 415 nm with switching threshold ≈ 0.5 V*

All simulations were conducted at a supply voltage of **V<sub>DD</sub> = 1 V**.

---

## ✅ Conclusion

This experiment highlights the **critical role of transistor sizing** in CMOS logic design:

- A balanced inverter with **symmetrical noise margins** and **optimized threshold** was achieved by tuning **PMOS width**.
- Such tuning is essential when designing for high performance, robust logic in deep submicron technologies.

The methodology demonstrated here forms a key foundation for more complex digital and mixed-signal IC design workflows.

---

## 👨‍💻 Author

**Amit Kiron Biswas**  
Electronics and Communication Enthusiast | Analog Design Learner  

*This repository is part of an academic exploration into the fundamentals of CMOS logic design.*

