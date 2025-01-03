Mod-N Counter

This repository contains the RTL design and testbench for a parameterized modulo-N counter. The counter is implemented in Verilog, supporting custom modulus (N) and bit-width (WIDTH) parameters for flexibility.

Overview:

The modulo-N counter generates a cyclical count from 0 to 𝑁−1,wrapping back to 0 after reaching 𝑁−1. It is a parameterized design, allowing users to adjust the modulus (N) and bit-width (WIDTH) to suit their specific applications.

Features:

Parameterized Design:
Modulus (N): Default is 10.
Bit-width (WIDTH): Default is 4.
Synchronous Operation:
Rising-edge triggered.
Asynchronous reset (rstn).
Automatically rolls over to 0 after reaching 𝑁−1.

RTL Code Description:

The RTL module (mod_n_rtl) implements the counter logic. Key highlights include:

Parameters:

N: Modulus of the counter (default: 10).
WIDTH: Bit-width of the counter (default: 4).
Inputs:

clk: Clock signal.
rstn: Active-low asynchronous reset signal.

Output:

out: Counter value.

Behavior:

Resets to 0 when rstn is low.
Increments on each clock cycle.
Rolls over to 0 when the count reaches N−1.

Testbench Description

The testbench (mod_n_tb) verifies the counter's functionality under various conditions:

Parameters:

N (modulus): 10.
WIDTH (bit-width): 4.

Inputs Generated:

clk: Clock signal with a period of 20 ns.
rstn: Reset signal initialized as active-low and later de-asserted.

Simulation scenarios:

Counter reset at startup.
Incrementing and wrapping around after reaching N−1.
The testbench uses $monitor to log the simulation results.

