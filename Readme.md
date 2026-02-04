# Simulation of CMOS Digital Circuits Using PSPICE

## Project Objective
- Design and simulate a CMOS digital circuit in PSPICE based on a Boolean expression.
- Implement complementary NMOS and PMOS transistors to realize digital logic.
- Demonstrate low-power CMOS logic and verify circuit functionality through simulation.

## Tools & Technologies
- **Software:** ORCAD PSPICE
- **Components:** NMOS and PMOS transistors, voltage sources
- **Logic:** CMOS logic gates (NAND, NOR, Inverter)
- **Other:** Probes for waveform analysis


### Metal-Oxide-Semiconductor Field-Effect Transistor (MOSFET) & CMOS Logic Overview

  - The **Metal-Oxide-Semiconductor Field-Effect Transistor (MOSFET)** is a voltage-controlled device widely used in digital circuits.
It has three terminals: **Gate (G)**, **Drain (D)**, and **Source (S)**.
MOSFETs offer extremely high input resistance and negligible gate current, making them ideal for digital switching.


MOSFETs are classified into **NMOS** and **PMOS** types.
These two devices operate in a complementary manner and together form the basis of **CMOS logic**, enabling high noise margin and reliable digital switching.

#### NMOS vs PMOS

<img src="images/MOS.JPG" alt="MOS" align="right" width="280" height="300" style="margin-left:20px; margin-bottom:0; margin-top:0;">


- **NMOS (N-channel MOSFET):**     
  - Built on P-type substrate, conducts when **gate voltage is HIGH** 
  - Exhibits higher electron mobility, resulting in faster switching speed
  - Commonly used in the **pull-down network (PDN)** of CMOS circuits.
 
- **PMOS (P-channel MOSFET):**
  - Built on N-type substrate, conducts when **gate voltage is LOW**
  - Complements NMOS to provide high noise margin and reliable digital switching in CMOS logic.
  - Used in the **pull-up network (PUN)** of CMOS circuits to provide a stable logic HIGH level.


#### MOSFET are available in two basic forms:
  - **Depletion Type MOSFET:** Conduction occurs at V<sub>GS</sub> = 0; requires a gate voltage of opposite polarity to switch OFF.                                      Included for conceptual understanding.
  
  - **Enhancement Type MOSFET:** Normally OFF and requires V<sub>GS</sub> > V<sub>th</sub> to turn ON; all devices in this project are                                     enhancement-mode, consistent with modern CMOS design practices.

### Complementary Metal-Oxide-Semiconductor (CMOS)


<img src="images/CMOS inverter.JPG" alt="NMOS" align="right" width="280" style="margin-left:20px; margin-bottom:10px;">


 - CMOS (Complementary Metal-Oxide-Semiconductor) logic employs both NMOS and PMOS transistors such that only one transistor network conducts in the steady state.
 - This complementary operation results in negligible static power dissipation, high noise immunity, and efficient switching behavior

A CMOS inverter consists of a **PMOS pull-up network** and an **NMOS pull-down network**.
  - When the input is HIGH, NMOS conducts and PMOS turns OFF, producing a LOW output.
  - When the input is LOW, PMOS conducts and NMOS turns OFF, producing a HIGH output.


#### Boolean Expression Using Logic Gates

The Boolean expression is first realized using conventional logic gates such as **NAND** and **NOR**. This step helps in verifying the correctness of the logic function before implementing it using MOS transistors.

Boolean Expression: Y = (A(B + CD))'

<p align="center">
  <img src="images/Gates.JPG" alt="Boolean Expression Using Logic Gates" width="600">
</p>

#### Boolean Expression Using MOS Transistors

#### CMOS LOGIC:

  In static CMOS logic, logic gates are implemented using complementary pull-up and pull-down networks:

  -	For implementing NAND gate N-MOS is connected in series and P-MOS in parallel.
  -	For implementing NOR gate N-MOS is connected in parallel and P-MOS in series.

This duality ensures correct logic functionality while maintaining very low static power dissipation.



### Steps to Realize Boolean Expression (`Y = (A(B + CD))'`)         

- **B:** Series in PMOS, parallel in NMOS                     <img src="images/Circuit.JPG" alt="MOS Implementation" align="right" width="300" height="800" style="margin-left:20px; margin-bottom:0; margin-top:0;"/>
- **C and D:** Parallel in PMOS, series in NMOS               
- **A:** Included in both PMOS and NMOS networks
- **Output Y:** Taken from the common drain node


#### CMOS Implementation Rules

<table>
<tr>
<th>Network</th>
<th>Series Connection</th>
<th>Parallel Connection</th>
</tr>
<tr>
<td><strong>NMOS</strong></td>
<td style="text-align:center;">AND</td>
<td style="text-align:center;">OR</td>
</tr>
<tr>
<td><strong>PMOS</strong></td>
<td style="text-align:center;">OR</td>
<td style="text-align:center;">AND</td>
</tr>
</table>

Note: The AND/OR terms describe the conduction behavior of NMOS and PMOS networks. The final gate logic (NAND/NOR) results from the complementary pull-up and pull-down configuration.

### Significance of CMOS in Digital Circuit Design
- Low Static Power Dissipation: Only negligible current flows in steady state; power is consumed primarily in switching events.
- High Integration Density: Complementary design allows more logic gates to be packed on a single chip.
- Robust Noise Margin: Reliable operation even under voltage fluctuations.
- Scalability: Supports large-scale integration, making it ideal for modern VLSI and high-performance digital systems.


### Simulation & Waveform Analysis

The PSPICE simulation files and waveform results are organized inside the `simulation/` directory.

- Circuit schematics, input sources, and model files are located in `simulation/`
- Output waveform plots are generated using PSPICE probes
- Detailed steps to run the simulation and view waveforms are provided in **[`simulation/README.md`](simulation/README.md)**

Refer to that file for simulator-specific instructions.

### Observations & Results
- Output waveform matches the Boolean expression for all input combinations
- Full voltage swing (0 V to VDD) confirms correct CMOS logic levels
- Complementary NMOS/PMOS switching observed, validating static CMOS behavior
- Static power dissipation is negligible; power is consumed mainly during switching

## Learning Outcomes
- Design and simulate CMOS digital circuits from Boolean expressions.
- Implement NMOS and PMOS networks for logic gates (NAND, NOR, Inverter).
- Verify circuit functionality using PSPICE and analyze output waveforms.
- Understand low-power operation and complementary CMOS behavior.### Simulation Procedure

## Project Nature
This lab experiment was completed as part of the **Circuits and Simulation Laboratory**, evaluated for semester practical examination. Focus: CMOS design, Boolean logic realization, PSPICE simulation, and low-power digital circuit verification.
