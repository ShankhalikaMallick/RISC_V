# 2. Labs using iVerilog & GTKwave

In this subdivision, I worked on **practical labs** using iVerilog and GTKwave to simulate and verify RTL designs.  

---

## 🎯 What I Learned
During these sessions, I learned:  
- How to organize my workspace by creating a **VSD folder** and a **VLSI subfolder** for lab files.  
- How to **clone a GitHub repository** containing the Sky130 RTL designs (from Kunal Ghosh sir) and explore its contents.  
- How to use **iVerilog** to compile and simulate a design module along with its testbench.  
- How to generate a **VCD file** from the simulation and visualize the output using **GTKwave**.  
- How to analyze module and testbench files using **gvim**.

---

## 🔹 Lab Setup
1. Created the following folder structure on my machine:  
            VSD -> VLSI
2. Cloned the Sky130 RTL repository (https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git) into the `VLSI` folder.  
3. Explored the repository files to understand the organization and RTL modules.  

---

## 🔹 Exploration of SKY130RTL repo
<img width="527" height="271" alt="image" src="https://github.com/user-attachments/assets/43cfdd81-e128-4042-88e6-cbb6c4bfd13c" />
<img width="1062" height="219" alt="image" src="https://github.com/user-attachments/assets/09398001-ba2d-4786-badb-6534ad192ac9" />
<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/519a8d7d-e5cd-4d15-b9f6-50ed85af6b7d" />

## 🔹 Simulation with iVerilog
- Took the example **mux** design: `good_mux.v`  
- Used the testbench: `tb_good_mux.v`  
- Simulated using the command:  
```bash
iverilog good_mux.v tb_good_mux.v  ## create executable file (a.out)
./a.out ## dump the vcd file and create tb_good_mux.vcd
gtkwave tb_good_mux.vcd ## Used to view the waveform
```
## 🔹 Viewing Results in GTKwave

I opened the generated VCD file in **GTKwave** to visualize the output.  

I observed how input changes affected the output, verifying that the design worked correctly.  

<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/053a822b-a1d8-4659-bc3c-827c2c5e5dcb" />

<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/4d393463-7377-4f53-bdc1-958edb33f4ee" />

---

## 🔹 File Analysis

In the second part of the lab, I analyzed the **module** and **testbench** files using **gvim**.  

I learned how to navigate through the code and understand signal connections and behavior.  

<img width="1187" height="214" alt="image" src="https://github.com/user-attachments/assets/5552e180-ce28-4ea1-b68d-a9987e0ee4af" />
<img width="1187" height="86" alt="image" src="https://github.com/user-attachments/assets/bfbdf4a5-b864-4379-bd4c-fb9328addeed" />
<img width="1216" height="297" alt="image" src="https://github.com/user-attachments/assets/cc793328-e1a3-4b85-852e-58755319ba36" />
<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/5e762230-c1d4-4d81-b722-0542404705e8" />

---

## 📝 Notes

The general commands to create a executable file of a design and run the simulation using iVerilog and gtkwave are:  

```bash
iverilog  < module_name.v > < testbench_name.v >
./a.out
gtkwave < testbench_name.vcd > 
gvim <module name>
gvim <testbench name>
```
