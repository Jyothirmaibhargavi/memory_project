1 KB Memory Module (Verilog)
📌 Overview

This project implements a 1 KB synchronous memory module in Verilog.
The memory supports read and write operations with parameterized width and depth, using a valid-ready handshake mechanism for data transfers.

🔧 Features

1 KB storage capacity (1024 × 8-bit locations).

Single-port memory with controlled read and write.

Reset mechanism to clear memory contents.

Valid-Ready handshake for safe communication.

Fully synchronous operation (triggered on positive clock edge).

📊 Configuration

Data Width (WIDTH): 8 bits (1 byte per memory location)

Memory Depth (DEPTH): 1024 locations

Address Width (ADDR_WIDTH): 10 bits (to address 1024 locations)

Total Size: 1024 × 8 bits = 8192 bits = 1 KB

📊 Working Principle

Reset (res = 1):

Clears all memory contents.

Resets output data and handshake signals.

Write Operation (wr_rd = 1, valid = 1):

Data (wdata) is stored into the memory location at the given address (addr).

The ready signal goes high to acknowledge the operation.

Read Operation (wr_rd = 0, valid = 1):

Data from the specified address is placed on the output (rdata).

The ready signal acknowledges that valid data is available.

Idle State (valid = 0):

No read or write operation occurs.

The ready signal remains low.

📊 Port Description
Signal	Direction	Width	Description
clk	Input	1	Clock signal, synchronizes all operations.
res	Input	1	Reset, clears memory and outputs.
wr_rd	Input	1	Write = 1, Read = 0.
valid	Input	1	Indicates a valid memory request.
addr	Input	10	Address for memory access (0–1023).
wdata	Input	8	Data to be written into memory.
rdata	Output	8	Data read from memory.
ready	Output	1	Indicates completion of read/write.
🚀 Applications

Register file in processors.

Temporary data storage in digital circuits.

Cache memory or buffer storage.

Lookup tables (LUTs) in digital systems.

Basic RAM model for simulations.
