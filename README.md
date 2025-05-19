# PIPELINE-PROCESSOR-DESIGN

COMPANY :CODTECH IT SOLUTIONS

NAME :B.SAISRIMA

INTERN ID :CT04DM37

DOMAIN : VLSI

DURATION : 4 WEEKS

MENTOR : NEELA SANTHOSH

#DESCRIPTION :implementation of a **4-stage pipelined processor** that supports basic instructions such as `ADD`, `SUB`, and `LOAD`:

---
**Design and Implementation of a 4-Stage Pipelined Processor**

The objective of this project was to design a simple **4-stage pipelined processor** capable of executing basic instructions: `ADD`, `SUB`, and `LOAD`. This processor demonstrates how pipelining improves instruction throughput by overlapping different stages of instruction execution. Each instruction passes through four distinct stages, allowing multiple instructions to be in different stages of execution simultaneously.

---

 **Processor Pipeline Stages**

The pipeline consists of the following four stages:

1. **Instruction Fetch (IF)**: In this stage, the processor fetches the instruction from memory using the Program Counter (PC). The PC is then incremented to point to the next instruction.

2. **Instruction Decode (ID)**: The fetched instruction is decoded to determine the operation type. During this stage, the necessary registers are also read from the register file.

3. **Execute (EX)**: The actual operation is performed in this stage. For `ADD` and `SUB`, this involves arithmetic operations using the ALU. For the `LOAD` instruction, this stage calculates the memory address from which to fetch data.

4. **Write Back (WB)**: The result from the Execute stage is written back to the destination register in the register file.

---

**Instruction Set and Format**

The processor supports the following instructions:

* `ADD R1, R2, R3`: Adds the contents of R2 and R3, stores the result in R1.
* `SUB R1, R2, R3`: Subtracts R3 from R2, stores the result in R1.
* `LOAD R1, offset(R2)`: Loads a value from memory address (R2 + offset) into R1.

Each instruction is represented in a simplified RISC-style format, making decoding and execution straightforward.

---

**Design Implementation**

The processor was modeled using a high-level simulation in Python to validate the pipeline logic. Registers are represented as an array, and memory is simulated with a list. Instructions are stored in a list and fetched sequentially.

Each pipeline stage holds data for one instruction, and in each clock cycle, the instructions move forward through the pipeline. For example, when one instruction is in the Execute stage, the next one is being decoded, while a third is being fetched.

In this simplified design, no data forwarding or hazard detection is implemented. As a result, care must be taken with instruction ordering to prevent data hazards. Alternatively, NOPs (no-operation instructions) can be inserted manually to avoid conflicts.

---
 **Simulation and Results**

The simulation tracks the state of each instruction as it passes through the pipeline stages cycle by cycle. The results demonstrate overlapping execution, where multiple instructions are processed at once in different pipeline stages. This results in higher throughput compared to a non-pipelined processor, where each instruction must complete all stages before the next begins.

For example, after an initial fill latency of three cycles, the processor completes one instruction per cycle, illustrating the performance benefit of pipelining.

---

**Conclusion**

This project successfully demonstrates the fundamental concept of instruction pipelining in processor architecture. By dividing instruction execution into fetch, decode, execute, and write-back stages, and allowing instructions to flow through these stages in parallel, the processor achieves improved efficiency. While basic in its current form, the design can be expanded to include hazard detection, forwarding, branching, and a larger instruction set in future iterations.

