# 🛠️ Task 2 - Tool Installation and Setup  

## 🎯 Objective  
To install and verify the essential tools required for the **RISC-V SoC Tapeout project**:  
- **Icarus Verilog (iverilog)**  
- **GTKWave**  
- **Yosys**  

---


## 🌐 Virtual Machine Setup
Download Links:   
[VirtualBox Downloads](https://www.virtualbox.org/wiki/Downloads)   
[Ubuntu 24.04.3 LTS](https://ubuntu.com/download/desktop/thank-you?version=24.04.3&architecture=amd64&lts=true)
---

## 🖥️ System Check  

| **Requirement** | **Specification** |
|------------------|--------------------|
| RAM              | 6 GB              |
| HDD              | 50 GB             |
| OS               | Ubuntu 20.04+     |
| CPU              | 4 vCPU            |

---

## 1️⃣ Installing Icarus Verilog (iverilog)  

### 🔹 Installation Steps  
```bash
sudo apt-get update
sudo apt-get install iverilog
```
---
### 🔹 Terminal Output 
![iverilog Screenshot](.Screenshots/iverilog.jpg)

## 2️⃣ Installing GTKWave  

### 🔹 Installation Steps  
```bash
sudo apt-get update
sudo apt install gtkwave 
```
---
### 🔹 Terminal Output
![GTKWave Screenshot](.Screenshots/gtkwave.jpg)

## 3️⃣ Installing Yosys  

### 🔹 Installation Steps  
```bash
$ sudo apt-get update
$ sudo apt-get install yosys
$ which yosys
(this will give you the location of yosys in the ubuntu file)
$ /usr/bin/yosys
```
---
### 🔹 Terminal Output

<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/3e0de7b6-5481-4bf3-97ad-903d9c7140ed" />



## ✅ Outcome  
- Installed and verified: **Icarus Verilog**, **GTKWave**, and **Yosys**.  
- Tools are ready for **simulation, waveform analysis, and synthesis**.  
