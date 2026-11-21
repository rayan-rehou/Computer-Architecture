# 8-Bit Processor on FPGA

A simple 8-bit accumulator-based CPU built in **Intel Quartus Prime** for the **Altera DE2-115 (Cyclone IV E)** board, as part of a computer architecture course at the University of Ottawa.

## What's inside

| Block | File | Role |
|---|---|---|
| 8-bit ALU | `alu8bits.bdf`, `alu1bit.bdf`, `fulladder1bit.bdf` | Arithmetic and logic operations, built from 1-bit slices |
| Registers | `register8bits.bdf`, `register1bit.bdf` | Accumulator (AC), Data (DR), Address (AR), Instruction (IR) registers |
| Program counter | `counter8bits.bdf`, `counter4bits.bdf`, `counter1bit.bdf` | Steps through program memory |
| Control unit | `lab4controller.bdf`, `sc_ctrl.bdf`, `controlregister.bdf` | Decodes each instruction and drives the load, increment, bus and ALU select signals |
| Bus | `busmultiplexer.vhd` | 8-to-1 multiplexer that picks which value goes on the shared bus |
| Memory | `ram256x8.vhd`, `memorycontents8.mif` | 256 x 8 RAM holding the program and data |
| Display | `sevensegcontroller.bdf`, `seg7.vhd` | Shows register values on the 7-segment displays |
| Top level | `lab4top.bdf` | Connects everything: datapath, controller, RAM, DIP switches, displays |

## Test program

`memorycontents8.mif` contains a machine-code program that computes the **Fibonacci sequence (1, 1, 2, 3, 5, 8, 13)** and writes each value to memory.
`checker.sv` watches the memory writes and flags each correct value, and `Test1.vwf` is the waveform simulation used to verify it.

## Tools
Intel Quartus Prime 13.0 SP1 · Cyclone IV E (EP4CE115F29C7) · VHDL · SystemVerilog · block diagrams (BDF)
