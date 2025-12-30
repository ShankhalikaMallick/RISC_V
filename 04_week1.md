# Week 1 - RISC-V SoC Journey (Shankhalika Mallick)

![GitHub repo size](https://img.shields.io/github/repo-size/ShankhalikaMallick/RISC_V)
![GitHub contributors](https://img.shields.io/github/contributors/ShankhalikaMallick/RISC_V)

This repository documents the work done in **Week 1** of my **RISC-V SoC Tapeout project**

---

##  Table of Contents

- [Week 1 - RISC-V SoC Journey (Shankhalika Mallick)](#week-1---risc-v-soc-journey-shankhalika-mallick)
- [Repository Structure](#repository-structure)
- [Week 1 Topics Covered](#week-1-topics-covered)
- [Tools Used](#tools-used)
- [What I Learned](#what-i-learned)
- [Next Steps](#next-steps)
- [Credits & Acknowledgments](#credits--acknowledgments)


---

##  Repository Structure

---

### Day-1

- 1-Introduction-to-iVerilog                  [05_task3.md](./05_task3.md)  

- 2-Labs-using-iVerilog-GTKwave               [06_task4.md](./06_task4.md) 
 
- 3-Introduction-to-Yosys-Logic-Synthesis     [07_task5.md](./07_task5.md) 
 
- 4-Labs-using-Yosys-Sky130-PDK               [08_task6.md](./08_task6.md)

---

### Day-2

- 5-Introduction-to-Timing-Libraries  [09_task7.md](./09_task7.md)

- 6-Hierarchical-vs-Flat-Synthesis    [10_task8.md](./10_task8.md)

- 7-Various-Flop-Coding-Styles-and-Optimizations    [11_task9.md](./11_task9.md)

---

### Day-3

- 8-Introduction-to-Optimization    [12_task10.md](./12_task10.md)

- 9-Combinational-Logic-Optimization    [13_task11.md](./13_task11.md)

- 10-Sequential-Logic-Optimization    [14_task12.md](./14_task12.md)

- 11-Sequential-Optimization-for-Unused-Outputs    [15_task13.md](./15_task13.md)

---

### Day-4

- 12-GLS-and-Synthesis–Simulation-Mismatch   [16_task14.md](./16_task14.md)

- 13-Blocking-vs-Non-Blocking-Mismatch    [17_task15.md](./17_task15.md)

- 14-Labs-on-GLS-and-Synthesis–Simulation-Mismatch    [18_task16.md](./18_task16.md)

- 15-Labs-on-Synthesis–Simulation-Mismatch-for-Blocking-Statements    [19_task17.md](./19_task17.md)

---

### Day-5

- 16-If-and-Case-Constructs    [20_task18.md](./20_task18.md)

- 17-Incomplete-If-and-Case-Statements    [21_task19.md](./21_task19.md)

- 18-Incomplete-and-Overlapping-Case-Statements    [22_task20.md](./22_task20.md)

- 19-For-Loop-and-Generate-Constructs    [23_task21.md](./23_task21.md)

- 20-Labs-on-For-Loop-and-Generate    [24_task22.md](./24_task22.md)

---

## Week 1 Topics Covered

- **Day-1**: Introduction to Verilog RTL Design and Synthesis.  
- **Day-2**: Timing Libs, Hierarchical vs Flat Synthesis & Efficient Loop Coding Styles.
- **Day-3**: Combinational and Sequential Optimization.  
- **Day-4**: GLS, Blocking vs Non-Blocking & Synthesis-Simulation Mismatch.  
- **Day-5**: Optimization in Synthesis.

### Each day folder contains:
- Basic definition
- Verilog code files
- Simulation files and screenshots
- Synthesized printing stats and graphical representation of the design
- README describing tasks and observations

---
## Tools Used 

| Tool                     | Purpose / Use Case                                      |
|--------------------------|--------------------------------------------------------|
| Icarus Verilog (iverilog)| Compiling and simulating Verilog code    |
| GTKWave                  | Viewing and analyzing waveform outputs                |
| Yosys                    | Synthesizing Verilog designs to gate-level netlists   |

---

##  What I learned
- Understood the need of simulator and synthesizer.
- Got hands on with digital designs using the tools.
- Understood the importance of library files (.lib) and the cells present in it
- Understood the flow of synthesis and types of synthesis using the synthesizer `yosys`
- Understood the combinational and sequential design optimization in rtl
- Understood the concept and need of Gate level Simulation, blocking & non-blocking contructs and synthesis-simulation mismatch.
- Understood how optimization makes the design simple and reduce the area and power of a chip.
- Finally realized efficient coding styles for flops, looping constructs, combinational and sequential logic.

---

## Next Steps
- Continue documenting tasks for upcoming weeks.
- Maintain consistency in structure for all weeks.

---


## Credits & Acknowledgments
I would like to express my gratitude to:

- **Kunal Ghosh**, Founder of **VLSI System Design (VSD)** and his team, for providing this wonderful opportunity and platform.
- **IIT Gandhinagar** for collaborating and supporting the RISC-V SoC Tapeout program.
- The VSD community, which is actively contributing to building India's semiconductor ecosystem and leading towards self-reliance in chip design and innovation.
- This initiative will truly accelerate India's growth in semiconductors, empower students and professionals, and inspire future VLSI engineers.
- **Divya Darshan** for the awesome repository documentation and sharing with other students
---
