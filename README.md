# ⚡ femtoRV32: RISC-V FPGA Implementation

![Verilog](https://img.shields.io/badge/Language-Verilog-blue?style=for-the-badge&logo=verilog)
![Architecture](https://img.shields.io/badge/Arch-RISC--V-red?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Milestone%203%20Complete-success?style=for-the-badge)

A 3-stage pipelined processor core implementing the **RISC-V RV32I** instruction set architecture. Designed for FPGA synthesis, this project features a custom decomposition unit for compressed instructions and hardware-level hazard handling.

> **Team Overclock:** Developed as part of the CSCE 3301 Computer Architecture course (Spring 2025).

---

## 🚀 Key Features

### 1. 3-Stage Pipeline Architecture
* **Design:** Implements a classic Fetch-Decode-Execute pipeline.
* **Hazard Management:** Includes logic to handle **Read-After-Write (RAW)** data dependencies without stalling, ensuring optimal throughput.
* **Control Flow:** Handles `ECALL`, `EBREAK`, and `FENCE` as pipeline-stopping events for precise exception handling.

### 2. Full RV32I Compliance
* **Instruction Set:** Supports the complete base integer set of **42 instructions** (Arithmetic, Logical, Load/Store, Branching).
* **Memory Model:** Byte-addressable Von Neumann architecture (Unified Instruction & Data Memory).

### 3. Advanced Decoding
* **Decomposition Unit:** A specialized hardware module that decomposes compressed instructions into standard 32-bit instructions on the fly.

### 4. Custom Tooling
* **Python Program Generator:** A custom Python script that assembles instructions into machine code for the simulation environment.
* **External Loading:** Supports loading instruction hex files dynamically outside the Vivado synthesis loop.

---

## 🛠️ Tech Stack & Tools

* **HDL:** SystemVerilog / Verilog
* **Architecture:** RISC-V (RV32I Base Integer ISA)
* **Simulation & Synthesis:** Xilinx Vivado
* **Scripting:** Python (Testbench generation)

---

## 🚧 Design Limitations & Assumptions
* **Arithmetic:** Mul/Div extensions are not currently supported (software emulation required).
* **Branch Prediction:** Static branch prediction (assumes branch not taken); no dynamic predictor implemented.
* **Memory:** Assumes a single unified memory block for both instructions and data.

---

## 👥 Team Overclock
* **Ebram Thabet**
* **Eman Abd ElHady**

---

## 📜 References
* [RISC-V Unprivileged Instruction Set Specification](https://riscv.org/specifications/ratified/)

---

## ⚠️ Academic Integrity Disclaimer
This project was created for the CSCE 3301 course (Spring 2025). It is published here for **educational and portfolio purposes only**. Current students should not copy this HDL code for their own assignments.
