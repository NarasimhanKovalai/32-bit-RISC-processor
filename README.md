# 32-bit 5-Stage Pipeline (Logisim)
Refer to Final Circuit.circ logisim file to load the processor onto logisim. Implementation Circuit.pdf contains details on each of the components in the procesor.Instruction Encoding.pdf contains the naive ISA design used.

Note that the only similarity to RISC pipeline is the classic 5 stage pipeline. We have not implemented the exact ISA (privileged or unprivileged) and other specs like zicr and CSR registers.

This project implements a five-stage 32-bit pipeline with a simplified instruction set. The pipeline includes:

- A hardwired control unit.
- A dual-port register unit with 32 general-purpose registers (GPRs).
- 24-bit wide memory addresses (maximum size usable in Logisim).
- 32-bit wide data paths.

---

##  Steps to Run the Program in Logisim

1. **Reset the Circuit**  
   Click the reset button or press `Ctrl + R` to reset the circuit to its default configuration.

2. **Set Stage Counter**  
   Manually set the counter to `4` (this implies that stage 5 is complete), so the pipeline starts afresh from stage 1.  
   - Right-click the control unit to access and modify the counter.

3. **Load Instructions**  
   - Use the **poke tool** to access memory.
   - Load instructions using a memory image (`Load Image` option).
   - Instructions can start from any base address.

4. **Set Program Counter (PC)**  
   - Using the **poke tool**, double-click the fetch unit and set the PC to the base address of the first instruction.

5. **Start Execution**  
   - Press `Ctrl + K` to enable the clock trigger and begin execution.

6. **Run Until Halt**  
   - Wait until the `Halt` instruction is executed.
   - Once the halt instruction is encountered, the stage counter stops, indicating completion.

7. **View Results**  
   - Results can be viewed at specific RAM addresses, depending on the program being executed.

---
##  Supported Instructions

The processor supports the following instructions and their immediate value versions:

- `ADD`, `SUB`, `MOVE`, `LOAD`, `STORE`, `OR`, `AND`, `HALT`
Branching and branch prediction may be added in later revision.
---

##  Notes

- The memory address size is restricted by Logisim to 24 bits.
- Ensure your program includes a `Halt` instruction for proper termination.
