# 8-to-1 Multiplexer in Verilog

This repository contains Verilog HDL code and a testbench for an 8:1 multiplexer.

## Files

- `mux8to1.v` - Main Verilog module
- `tb_mux8to1.v` - Testbench for simulation

## How It Works

The multiplexer selects one of the 8 input lines (`data_in[7:0]`) based on the 3-bit select line (`sel[2:0]`).

### Example:
If `data_in = 8'b10101010` and `sel = 3'b010`, then output `out = data_in[2] = 1`.
