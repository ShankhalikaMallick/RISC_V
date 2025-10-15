# RISC_V

## CORE DESIGN OF A RISC-V PROCESSOR RV32I BASE INSTRUCTION SET ARCHITECTURE (ISA)

**RV32I** is a 32-bit version of the RISC-V processor that uses a basic set of instructions for handling integer operations.   
It is designed and implemented using **Verilog HDL** , a hardware description language used to build digital circuits.  

### INTRODUCTION
This project implements a simple RISC-V processor using the RV32I base instruction set architecture (ISA) , which defines a simple 32-bit integer core.
The RV32I ISA includes different instruction types such as R-type, I-type, S-type, B-type, U-type, and J-type, covering basic arithmetic, logic, memory, and control operations.
The processor is designed in **Verilog HDL** and operates on a single clock cycle per instruction, with no pipelining.  

### THIS REPOSITORY CONTAINS:
1. [TOP_RISCV_TB]()  
It is the test bench driving the top module. It generates clock and reset signals and checks the proper working of the modules.  
   
3. [TOP_RISCV](https://github.com/ShankhalikaMallick/RISC_V/blob/main/TOP_RISCV.v)   
The top module controls the working of other units IFU, IMU, CU, DPU, IMM_GEN. It is driven by top module testbench.  

4. [instruction_fetch_unit]()
5. [instruction_memory_unit]()
6. [control_unit]()
7. [data_path_unit]()
8. [immediate_generator]()
9. 
