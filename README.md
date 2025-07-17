# 8-to-1 Multiplexer in Verilog

This repository contains Verilog HDL code and a testbench for an 8:1 multiplexer.

## Files

- `mux8to1.v` - Main Verilog module
- `tb_mux8to1.v` - Testbench for simulation

## How It Works

The multiplexer selects one of the 8 input lines (`data_in[7:0]`) based on the 3-bit select line (`sel[2:0]`).

### Example:
If `data_in = 8'b10101010` and `sel = 3'b010`, then output `out = data_in[2] = 1`.


## 📘 Project Description – 8-to-1 Multiplexer using Verilog HDL

This project implements an **8-to-1 Multiplexer** (MUX) using **Verilog Hardware Description Language (HDL)**. Multiplexers are key components in digital systems, used to route data from multiple input lines to a single output line based on a control signal.

In this design, we use:
- **8 input lines** (`data_in[7:0]`)
- A **3-bit select line** (`sel[2:0]`)
- And one output line (`out`) that reflects the selected input.

The main objective of this project was to **understand combinational logic design** and **practice Verilog coding**, simulation, and testbench writing.

---

## 🛠️ Design Explanation

- The `sel` signal determines which bit from `data_in` gets passed to the `out`.
- Since we have 8 inputs, a 3-bit select line (2³ = 8) is used.
- The implementation is efficient and clean, using a single line of code:
  
  ```verilog
  assign out = data_in[sel];
