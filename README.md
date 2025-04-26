# Current Mode Logic (CML) Circuits – VLSI Design

Welcome to my repository showcasing a detailed collection of **Current Mode Logic (CML)** digital circuits, designed and simulated using **Cadence Virtuoso** at the **180 nm technology node**. This work demonstrates my systematic approach to high-speed differential logic design and my proficiency with industry-standard EDA flows.

---

## Table of Contents

1. [Why Current Mode Logic (CML)?](#why-current-mode-logic-cml)  
2. [Technology and Tools](#technology-and-tools)  
3. [Implemented Circuits](#implemented-circuits)  
   1. [CML Buffer / Inverter](#1-cml-buffer--inverter)  
   2. [CML NOR / OR Gate](#2-cml-nor--or-gate)  
   3. [CML AND / NAND Gate](#3-cml-and--nand-gate)  
   4. [2×1 CML Multiplexer](#4-2×1-cml-multiplexer)  
   5. [CML D Latch – Positive Level Triggered](#5-cml-d-latch–positive-level-triggered)  
   6. [CML D Latch – Negative Level Triggered](#6-cml-d-latch–negative-level-triggered)  
   7. [CML D Flip-Flop – Positive Edge Triggered](#7-cml-d-flip-flop–positive-edge-triggered)  
4. [Propagation Delay Observations](#propagation-delay-observations)  
5. [Conclusion](#conclusion)  
6. [Author](#author)  

---

## Why Current Mode Logic (CML)?

Although CMOS logic remains the ubiquitous choice for digital systems—thanks to its near-zero static power and design simplicity—its rail-to-rail switching and dynamic current spikes can hinder performance in ultra-high-speed or precision applications. **Current Mode Logic** addresses these limitations by:

- **Limiting Voltage Swing:** Only a small differential voltage is toggled, yielding faster transitions.  
- **Using Constant Current Biasing:** The tail current source provides a stable bias, reducing supply noise and limiting di/dt.  
- **Employing Differential Signaling:** Enhances noise immunity and signal integrity, critical in SerDes and clock distribution networks.  
- **Achieving High Throughput:** Ideal for multi-Gbps links, PLL clock drivers, and mixed-signal front-ends.  

These attributes make CML the architecture of choice for **high-frequency I/O, SerDes channels, and precision clocking circuits**.

---

## Technology and Tools

- **Process Technology:** 180 nm CMOS  
- **Design Environment:** Cadence Virtuoso v6.1.8  
- **Simulation Engine:** Spectre  
- **Design Style:** Differential current-steering pairs with NMOS tail-current sources  
- **Key Focus:** Delay optimization, signal fidelity, and robust biasing  

---

## Implemented Circuits

### 1. CML Buffer / Inverter

**Schematic:**  
![Buffer Schematic](./CML_Buffer_Inverter/schematic.png)

**Transient Response:**  
![Buffer Waveform](./CML_Buffer_Inverter/waveform.png)

A basic differential pair with resistive loads and an NMOS tail source. Demonstrates clean inverting action with sub-100 ps delay (example).

---

### 2. CML NOR / OR Gate

**Schematic:**  
![NOR OR Schematic](./CML_OR_NOR/schematic.png)

**Transient Response:**  
![NOR OR Waveform](./CML_OR_NOR/waveform.png)

Implements NOR and OR by steering currents through parallel differential branches. Ensures minimal skew between outputs.

---

### 3. CML AND / NAND Gate

**Schematic:**  
![AND NAND Schematic](./CML_AND_NAND/schematic.png)

**Transient Response:**  
![AND NAND Waveform](./CML_AND_NAND/waveform.png)

Uses stacked differential pairs to realize AND/NAND logic. Carefully sized devices optimize fan-in versus speed trade-offs.

---

### 4. 2×1 CML Multiplexer

**Schematic:**  
![2x1 MUX Schematic](./CML_2x1_MUX/schematic.png)

**Transient Response:**  
![2x1 MUX Waveform](./CML_2x1_MUX/waveform.png)

Selects one of two differential inputs. Highlights low-glitch switching and minimal propagation penalty.

---

### 5. CML D Latch – Positive Level Triggered

**Schematic:**  
![D Latch Pos Schematic](./CML_D_Latch_Pos/schematic.png)

**Transient Response:**  
![D Latch Pos Waveform](./CML_D_Latch_Pos/waveform.png)

Samples input when clock is high; holds data when low. Demonstrates robust level-sensitive behavior.

---

### 6. CML D Latch – Negative Level Triggered

**Schematic:**  
![D Latch Neg Schematic](./CML_D_Latch_Neg/schematic.png)

**Transient Response:**  
![D Latch Neg Waveform](./CML_D_Latch_Neg/waveform.png)

Complementary to the positive latch, sampling on clock low and holding on high.

---

### 7. CML D Flip-Flop – Positive Edge Triggered

**Schematic:**  
![DFF Schematic](./CML_DFF_Pos_Edge/schematic.png)

**Transient Response:**  
![DFF Waveform](./CML_DFF_Pos_Edge/waveform.png)

Master-slave configuration capturing data on the rising clock edge, combining two level-sensitive latches.

---

## Propagation Delay Observations

Below is a summary of the **propagation delays** I measured during transient simulation—these values reflect my performance optimizations and device sizing choices.

| **Circuit**                         | **Measured t<sub>pd</sub>** |
|------------------------------------|-----------------------------|
| CML Buffer / Inverter              | XX ps                       |
| CML NOR / OR Gate                  | XX ps                       |
| CML AND / NAND Gate                | XX ps                       |
| 2×1 CML Multiplexer                | XX ps                       |
| CML D Latch (Positive Level)       | XX ps                       |
| CML D Latch (Negative Level)       | XX ps                       |
| CML D Flip-Flop (Pos Edge Trigger) | XX ps                       |

*(Values to be updated with actual simulation results.)*

---

## Conclusion

This repository encapsulates my methodical exploration of CML logic, from fundamental gates to sequential elements. The designs highlight my skills in:

- High-speed differential circuit topology  
- Precision biasing and device sizing  
- Transient and noise-immunity optimization  

These building blocks serve as a solid foundation for complex SerDes channels, low-jitter clock distribution, and mixed-signal integration.

---

## Author

**Harshit Srivastava**  
Analog Design Engineer & VLSI Enthusiast  
[LinkedIn](#) • [Email](#harshitsri117@gmail.com)  

