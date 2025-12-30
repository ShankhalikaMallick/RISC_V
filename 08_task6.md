
# 4. Labs using Yosys & Sky130 PDK

In this final subdivision of Day 1, I performed **hands-on labs using Yosys** along with the **Sky130 PDK** to synthesize and realize a simple MUX design. The lab was divided into three parts.  

---

## What I Learned
During this session, I understood:
- How to load a standard cell library in Yosys using `read_liberty`.  
- How to import an RTL Verilog design using `read_verilog`.  
- The synthesis flow in Yosys from RTL to intermediate representation using `synth`. 
- How to write the synthesized gate-level netlist using `write_verilog`. 
- Importance of organizing commands and outputs to track the synthesis process.  


---

## 🔹 Part 1: Reading Library and Synthesizing RTL

1. **Read the library file (.lib)** using the command:
- enter the lib folder and run yosys
- check the contents and read_liberty
- this loads a standard cell library into yosys

```bash
read_liberty -lib <path_to_library_file>
``` 

- <path_to_library_file> can be a relative or absolute path.
- Terminal showing `read_liberty` command output 

<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/229c6513-f79d-4828-9294-c6e64a8a65cf" />

---

## Read the Verilog module

```bash
read_verilog good_mux.v
```
- Loads the RTL design into Yosys.
- Terminal showing `read_verilog` output
  
<img width="1216" height="207" alt="image" src="https://github.com/user-attachments/assets/d68379ce-20e4-4029-acee-708845966272" />

---

## Synthesize the design

```bash
synth -top good_mux
```
- Converts the RTL to an intermediate representation.
- Terminal showing synthesis output 
<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/14d93393-91b8-465b-8fc9-957b756d6541" />

<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/5a4dcb6b-fae9-4bb3-a1a3-bfafb68e4cd2" />

<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/d7618284-f870-4554-a8e3-38d3343100e9" />

<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/74c4497a-c134-467d-be54-f417bb80b4c7" />


---

## Perform technology mapping with ABC

```bash
abc -liberty < path_to_library_file >
```
- Generates the **gate-level netlist** from the RTL.
- Terminal showing ABC output  

<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/8d80012c-22d2-476e-ace5-afb9a153ecd1" />

<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/66975c25-f9ec-48b0-8952-e99854742f0a" />

---

## Visualize the synthesized logic

- The command that Produces a graphical representation of the logic.
```bash
show
```
- Terminal Output

<img width="1216" height="271" alt="image" src="https://github.com/user-attachments/assets/aa8c31ef-4fc2-44f0-9add-e0de17ad01e8" />

--- 

-Graphical logic representation

<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/a2f51e22-8d44-4ae6-8c52-7b4c34939c38" />


---

## Part 2: Realization of MUX in Gates

### Write the netlist to a file

```bash
write_verilog -noattr good_mux_netlist.v
```
- The **-noattr** option removes extra attributes for cleaner output.
- The file name should be meaningful to maintain clarity in the repository.
- Terminal showing write verilog output
  
<img width="1216" height="221" alt="image" src="https://github.com/user-attachments/assets/ba47db2b-eec3-4e7a-b7df-7100637f91a8" />


---

### Open and Inspect the Netlist

```bash
!gvim good_mux_netlist.v
```
- Opens the generated netlist in gvim.
- Allows checking how the RTL design is translated into gate-level logic.
- gvim showing gate-level netlist

<img width="1216" height="135" alt="image" src="https://github.com/user-attachments/assets/fb188004-4d84-44dc-9f29-a25b2cc99ae9" />

<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/6abcebcb-deb7-43f0-bc50-cab3ad9ea31e" />


### Extra notes: 
if ghraphviz doesnt open and you get the error: ModuleNotFoundError: No module named 'distutils' then open another cmd and write 
```bash
$ sudo apt install python3-pip
```
