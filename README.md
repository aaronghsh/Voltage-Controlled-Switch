# Voltage Controlled Switches 🔌

This project investigates the behavior of real vs ideal electronic switches, with a focus on **MOSFET-based switch designs**. It includes simulations, physical testing, waveform analysis, and performance evaluation of two different switch configurations.

---

## Technologies & Tools Used

- **Analog Discovery 3 (AD3)**: Used for generating test signals, capturing waveforms, multimeter and oscilloscope for measurement/verification of ON/OFF behavior.
- **LTspice**: For simulating both switch designs.
- **nMOS and pMOS Transistors**: Used in complementary configurations for voltage-controlled switching.


---

## Features

- **Ideal vs. Non-Ideal Switch Behavior**:
  - Compared expected characteristics like zero resistance, infinite OFF resistance, and bidirectional current flow.
- **Real-World Testing**:
  - Verified ON resistance, OFF leakage current, voltage drops, and bidirectionality using real components.
- **Two Custom Switch Designs**:
  - **Switch 1**: Minimalist design using nMOS, pMOS, and a resistor.
  - **Switch 2**: More complex but efficient complementary configuration using voltage control.

---

## Test Objectives

1. **Measure ON State Resistance**: 
   - Using Ohm’s Law and measured current/voltage drops.
2. **Measure Leakage in OFF State**:
   - With the switch open, detect any current that leaks through.
3. **Test Bidirectionality**:
   - Reverse terminals and compare performance.
4. **Verify Voltage Limits**:
   - Gradually increase supply voltage to detect any operational thresholds.

---

## Switch 1 Overview

- **Design**: Uses complementary nMOS and pMOS with minimal components.
- **Simulation & Physical Testing**: Performed in LTspice and on breadboard.
- **Performance**:
  - ON resistance: ~345–487Ω
  - OFF resistance: Up to 9.2MΩ
  - Voltage drop in ON state: ~0.28V
  - Successful bidirectional operation
- **Trade-offs**:
  - Simple, low-noise design.
  - Limited by AD3’s 0–5V output range.
  - Best suited for low-cost, low-complexity applications.

---

## Switch 2 Overview

- **Design**: Enhanced voltage-controlled logic using two MOSFETs.
- **Performance**:
  - ON resistance: ~387–703Ω
  - OFF resistance: Over 11MΩ
  - Cleaner control logic via VCONTROL pin.
  - Slight non-linearities between 1.5–2.5V due to MOSFET saturation.
- **Trade-offs**:
  - Slightly more complex and costly.
  - Outperforms BJTs in power efficiency and thermal stability.
  - Less suitable for mass production compared to simpler switch designs.

---

## Summary of Results

| **Switch** | **ON Resistance (Ω)** | **OFF Resistance (Ω)** | **Bidirectional?** | **Notes** |
|------------|------------------------|-------------------------|--------------------|-----------|
| Switch 1   | 345 – 487              | ~923k – 9.2M            | ✅ Yes             | Simple & robust |
| Switch 2   | 387 – 703              | ~1.1M – 12M             | ✅ Yes             | Controlled via VCONTROL |

- Both switches confirmed bidirectional current flow.
- Minor inconsistencies in switching thresholds due to MOSFET characteristics.
- Measurements matched theoretical expectations closely.

---

## Project Files

- `Project 2 Switch 1.asc`, `Project 2 Switch 2.asc`: LTspice schematics for both designs.
- `Project 2 Documentation.pdf`: Complete documentation, design process, and analysis.
