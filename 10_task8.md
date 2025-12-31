# 2. Hierarchical vs Flat Synthesis

---

## What I Learned

- I explored the difference between **Hierarchical** and **Flat Synthesis** approaches in digital design.  
- I practiced synthesizing a **multi-module design** and observed how the **hierarchy affects the resulting netlist structure**.  
- I learned that **Hierarchical Synthesis** preserves module structure, improving **readability and modular verification**.  
- I learned that **Flat Synthesis** merges all modules into a **single top-level module**, enabling **global optimization** but reducing readability.  
- I understood how **submodule-level (modulable) synthesis** allows synthesizing specific modules for **large designs** or **repeated modules**.  


---

## Key Concepts

### Hierarchical Synthesis
- In **Hierarchical Synthesis**, each module is synthesized **separately** according to the design hierarchy.  
- Maintains the module structure in the netlist, which improves **readability** and **modular verification**.  
- Preferred when designs have **multiple instances of the same module** or when we want a **divide-and-conquer approach** to handle large designs.  

###  Flat Synthesis
- In **Flat Synthesis**, all modules are **flattened into a single top-level module** during synthesis.  
- Maximizes **global optimization** but can result in a **large, less readable netlist**.  
- Useful for smaller designs or when **module hierarchy is not required**.

### Modulable / Submodule-level Synthesis
- Allows synthesizing **only specific submodules** using:  
```bash
synth -top <module_name>
```
---

### How to do Hierachical synthesis

```bash
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```
- Reads the standard cell library (.lib) for synthesis. Provides timing, area, and power info for each cell.

```bash
read_verilog <module_name.v>
```
- Loads your Verilog RTL code into the tool. Prepares the design for synthesis.

```bash
synth -top <module_name>
```
- Synthesizes the RTL to a gate-level netlist. -top specifies the top-level module.

```bash
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```
- Performs technology mapping using ABC. Maps generic gates to standard cells in the .lib file.

```bash
show 
```
- Displays a graphical view of the synthesized netlist. Useful for visual inspection of circuit structure.
---

### Example – Hierarchical Synthesis Flow

For the design (`multiple_modules.v`), I executed the following commands:

```bash
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog multiple_modules.v
synth -top multiple_modules 
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show multiple_modules
write_verilog -noattr multiple_modules_hier.v
!gvim multiple_modules_heir.v
```
### Hierarchical Synthesis using (`synth -top multiple_modules`)

---

procedure:

<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/3d5150de-2c6e-4dad-99b7-9173d8e0528a" />

<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/72f0188f-88b4-4b6f-a274-851d02a64ba5" />

<img width="818" height="579" alt="image" src="https://github.com/user-attachments/assets/d4082996-0ea9-4fc9-8cae-6cf1679bf126" />

<img width="886" height="180" alt="image" src="https://github.com/user-attachments/assets/57645c33-5893-48f7-bfb3-773f91749dcb" />

<img width="886" height="110" alt="image" src="https://github.com/user-attachments/assets/efcc4519-2343-4cef-bfaa-82b04b0a9eca" />

<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/a22d817a-56b8-4327-a14a-7b9b2afc9fd7" />

<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/1ee6e298-5457-4e84-a5d0-932e7de9eeba" />

<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/80481676-f90b-4bde-b952-4fcf5d540859" />

<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/abcecbd4-1c59-4777-967d-1ddf448dbebf" />

<img width="1216" height="256" alt="image" src="https://github.com/user-attachments/assets/962ea5c2-f197-45e9-88e7-ff570817a68f" />

<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/212d0c46-4d25-4cce-807e-cc09420536b1" />


<img width="1216" height="256" alt="image" src="https://github.com/user-attachments/assets/4890309d-4a68-4995-8181-1175ac0aa2f4" />

<img width="1216" height="137" alt="image" src="https://github.com/user-attachments/assets/aa018bd8-c12a-4b0c-b174-ffb8df51892f" />

<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/e9d48995-c811-4367-8b67-afd164722ece" />

<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/7f5dc15c-72ad-4e75-a154-401fd50be718" />



---
### Observation

- After synthesis, the hierarchy is maintained, and the structure clearly shows submodules

---

### Example – Flat Synthesis Flow

To flatten the design:

```bash
write_verilog -noattr multiple_modules_flat.v
!gvim multiple_modules_flat.v
```

procedure:

<img width="1216" height="385" alt="image" src="https://github.com/user-attachments/assets/d4f0b2be-1787-4854-90f7-d12ab6ee5210" />


<img width="1216" height="768" alt="image" src="https://github.com/user-attachments/assets/fc957422-4ead-4aa4-b514-07e39c5744dd" />

<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/0c70c5bd-f8fe-4e39-a596-ba3fdd40c15b" />


---

### Observations:

- All modules are merged into a single file.
- No hierarchy is preserved.
- Useful for global optimization, but harder to read.

---
### Why Submodule-level Synthesis is Needed

Submodule-level (or modulable) synthesis is useful when we want to **synthesize only specific modules** instead of the entire design.  

**Key Reasons:**  

1. **Multiple Instances of the Same Module**  
   - When a design contains **many instances of the same module**, submodule-level synthesis allows **isolating and optimizing** that module independently.  

2. **Divide and Conquer for Large Designs**  
   - For very large designs, synthesizing the entire design at once can be inefficient.  
   - Submodule-level synthesis allows a **divide-and-conquer approach**, handling smaller parts individually to **manage complexity and resource usage**.  

**Command Used:**  

```bash
synth -top < module_name >
```
- This command controls which specific module is synthesized.
- It is particularly helpful in hierarchical designs to focus on a submodule without affecting other parts.

--- 

## Key Takeaways

- **Hierarchical Synthesis** keeps module structure intact, aiding **readability**, **modular verification**, and **divide-and-conquer synthesis**.  
- **Flat Synthesis** merges all modules for **maximum optimization** but sacrifices readability.  
- **Submodule-level (modulable) synthesis** allows control over which modules to synthesize, helpful in **large designs** or **repetitive modules**.
