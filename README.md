## Overview

This README provides detailed information about the Verilog implementation of a MIPS (Microprocessor without Interlocked Pipeline Stages) pipeline processor. The project covers the design and functionality of a pipelined MIPS processor, which includes instruction fetch, decode, execute, memory access, and write-back stages.

## Project Description

The MIPS pipeline processor is designed to execute instructions in a pipelined manner, improving instruction throughput by overlapping the execution of multiple instructions. This implementation includes five stages: Instruction Fetch (IF), Instruction Decode (ID), Execute (EX), Memory Access (MEM), and Write-Back (WB).

## Pipeline Stages

### 1. Instruction Fetch (IF)
- **Description:** Fetches the instruction from memory.
- **Key Components:** Program Counter (PC), Instruction Memory.
- **Functionality:** Increments the PC and fetches the next instruction.

### 2. Instruction Decode (ID)
- **Description:** Decodes the fetched instruction and reads the necessary registers.
- **Key Components:** Instruction Register, Register File, Control Unit.
- **Functionality:** Decodes the instruction to determine the operation, source operands, and destination registers.

### 3. Execute (EX)
- **Description:** Performs arithmetic or logical operations.
- **Key Components:** ALU (Arithmetic Logic Unit), ALU Control.
- **Functionality:** Executes the operation specified by the instruction.

### 4. Memory Access (MEM)
- **Description:** Accesses memory for load and store instructions.
- **Key Components:** Data Memory.
- **Functionality:** Reads from or writes to memory based on the instruction.

### 5. Write-Back (WB)
- **Description:** Writes the result back to the register file.
- **Key Components:** Register File.
- **Functionality:** Updates the destination register with the result of the operation.

## Components

- **Program Counter (PC)**
- **Instruction Memory**
- **Instruction Register**
- **Control Unit**
- **Register File**
- **ALU**
- **ALU Control**
- **Data Memory**
- **Pipeline Registers** (between each stage to hold intermediate data)

### Connections

1. **Instruction Fetch (IF) Stage:**
   - Connect the PC to the Instruction Memory.
   - Connect the output of the Instruction Memory to the Instruction Register.

2. **Instruction Decode (ID) Stage:**
   - Connect the Instruction Register output to the Control Unit and Register File.
   - Connect the Register File to the ALU for operand fetching.

3. **Execute (EX) Stage:**
   - Connect the ALU inputs to the operands from the ID stage.
   - Connect the ALU output to the MEM stage.

4. **Memory Access (MEM) Stage:**
   - Connect the ALU output and data from the register file to the Data Memory.
   - Connect the Data Memory output to the WB stage.

5. **Write-Back (WB) Stage:**
   - Connect the data from the MEM stage to the Register File for updating registers.

## References

- [MIPS Instruction Set Architecture](link_to_reference)
- [Verilog HDL Guide](link_to_reference)
- [Pipelined Processor Design](link_to_reference)
- [FPGA Programming Guide](link_to_reference)
