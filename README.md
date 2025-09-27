# RTL2GDS_MyJourney
🚀 A hands-on journey from RTL to GDSII with open-source EDA tools. This repo documents my work in the VSD RISC-V SoC Tapeout Program, covering synthesis, simulation, floorplanning, placement, routing, and sign-off checks. It serves as both a learning log and a reference for ASIC design with OpenLane.

Welcome to my repository! 🎉  
This project documents my hands-on experience with the RISC-V Reference SoC Tapeout Program (VSD).  

👉 The goal: take a design from 🔴 RTL Design ➝ 🔵 Synthesis ➝ 🟣 Physical Design ➝ 🎯 Tapeout Ready
 using **open-source tools** only.  


🌱 Week 0 – Foundation Week  

 *Environment Setup + Tool Installation* 🛠️  

Before designing silicon, the lab needs its instruments!  
This week focused on setting up the **complete RTL-to-GDSII toolchain**.  

✅ Tasks Completed  

| Task | Description | Status |
|------|-------------|--------|
| Task 0 | Install & verify the full EDA toolkit | ✔ Done |

🔧 Tools Installed & Verified  

| Tool | Purpose | Status |
|------|---------|--------|
| **Yosys** | RTL synthesis & logic optimization | ✅ Verified |
| **Icarus Verilog** | Verilog compilation & simulation | ✅ Verified |
| **GTKWave** | Waveform viewing & debugging | ✅ Verified |
| **Ngspice** | Analog & mixed-signal simulation | ✅ Verified |
| **Magic** | VLSI layout design + DRC check | ✅ Verified |



🎯 Program Objectives  

| Aspect | Focus |
|--------|-------|
| **Learning Path** | End-to-end SoC design: RTL ➝ Synthesis ➝ Physical ➝ Tapeout |
| **Tools** | Open-source EDA stack (Yosys, OpenLane, Magic, etc.) |
| **Industry Relevance** | Real-world semiconductor workflows |
| **Collaboration** | Part of India’s largest RISC-V tapeout initiative |
| **Scale** | 3500+ participants contributing |
| **Impact** | Strengthening India’s semiconductor ecosystem |



 🙏 Acknowledgments  

A huge thanks to [![Kunal Ghosh](https://img.shields.io/badge/GitHub-Kunal%20Ghosh-black?logo=github)](https://github.com/kunalghosh)
 and the VSD TEAM for leading this initiative 💡  

Also grateful to the supporting organizations:  

| Organization | Role | Impact |
|--------------|------|--------|
| **RISC-V International** | Open ISA leadership | Global ecosystem |
| **India Semiconductor Mission (ISM)** | Govt. initiative | National semiconductor strategy |
| **VLSI Society of India (VSI)** | Industry body | Professional growth |
| **Efabless** | Open-source tapeout platform | Democratizing silicon |


🚀 Mission Statement  

> *“Empowering the next generation of semiconductor engineers through open-source, hands-on silicon design.”*  


📅 Weekly Progress Tracker  

✔ Week 0 – Tools & setup complete  
🔜 Week 1+ – RTL design, synthesis, floorplanning, PnR, signoff, and tapeout readiness  

Stay tuned – the journey continues! 🌟  

my-learning-repo/
│
├── README.md
└── week1/
    ├── day01_setup.md
    ├── day02_rtl_basics.md
    ├── day03_verilog_intro.md
    ├── day04_simulation.md
    └── day05_assignment.md

# 🚀 Week 1 — RTL to GDS Journey

Welcome to **Week 1** of my RTL-to-GDS journey!  
This week focuses on **environment setup**, **RTL basics**, **Verilog simulation**, and a small **assignment**.  

Use the dropdowns below to explore **each day interactively** 👇



## 📂 Day 01 — Setup & Environment ✅

<details>
<summary>🎯 Goals</summary>

- Install required tools  
- Verify a minimal Verilog simulation  
- Generate first waveform  

</details>

<details>
<summary>🛠 Tools & Status</summary>

| Tool             | Installed? | Notes |
|-----------------|------------|-------|
| Icarus Verilog   | ⬜ | Simulation engine |
| GTKWave          | ⬜ | Waveform viewer |
| Yosys            | ⬜ | Synthesis tool |
| OpenROAD/OpenLane | ⬜ | PnR & GDS tools |

</details>

<details>
<summary>💻 Commands</summary>

```bash
sudo apt update
sudo apt install iverilog gtkwave yosys build-essential git
git clone <your-repo-url>
cd week1

# Test simulation
iverilog -o tb_blink.vvp tb_blink.v blink.v
vvp tb_blink.vvp
gtkwave dump.vcd

</details>

📂 Day 02 — RTL Basics ⚡
<details> <summary>🎯 Goals</summary>

Understand RTL concepts

Learn registers & data flow

Simulate a 4-bit counter

</details> <details> <summary>💻 Sample RTL Code</summary>

module counter (
    input clk,
    input rst_n,
    output reg [3:0] q
);
always @(posedge clk or negedge rst_n) begin
    if (!rst_n) q <= 4'b0;
    else q <= q + 1;
end
endmodule
</details> <details> <summary>💻 Commands</summary>

iverilog -o tb_counter.vvp tb_counter.v counter.v
vvp tb_counter.vvp
gtkwave counter.vcd
</details>

📂 Day 03 — Verilog Introduction ⚡
<details> <summary>🎯 Goals</summary>

Learn Verilog HDL syntax

Write basic logic gates

Run simple testbenches

</details> <details> <summary>💻 Example — AND Gate</summary>

module and_gate(input a, input b, output y);
    assign y = a & b;
endmodule
</details>

📂 Day 04 — Simulation ✅
<details> <summary>🎯 Goals</summary>

Run Icarus Verilog simulation

View waveforms in GTKWave

Debug RTL code

</details> <details> <summary>💻 Commands</summary>

iverilog -o tb_and.vvp tb_and.v and_gate.v
vvp tb_and.vvp
gtkwave dump.vcd
</details>

📂 Day 05 — Assignment 🎯
<details> <summary>🎯 Task</summary>

Implement basic logic gates in Verilog: AND, OR, NOT, NAND, NOR, XOR

Simulate each gate

Verify behavior

</details> <details> <summary>💻 Example — OR Gate</summary>

module or_gate(input a, input b, output y);
    assign y = a | b;
endmodule

</details> <details> <summary>✅ Progress Table</summary>
Gate	Done?	Notes
AND	✅	Tested
OR	✅	Tested
NOT	✅	Tested
NAND	⬜	Pending
NOR	⬜	Pending
XOR	⬜	Pending
</details>

📌 Key Takeaways

Installed toolchain successfully

Learned RTL basics & Verilog syntax

Ran first simulations

Completed assignment for basic gates


# 📘 `week1/day01_setup.md`

```markdown
# ⚡ Day 01 — Setup  

✅ Installed tools  
✅ Verified environment  
✅ First simulation run successful  



## 🔧 Commands Used
```bash
sudo apt update
sudo apt install iverilog gtkwave yosys build-essential git
git clone <your-repo-url>
cd week1

# Test simulation
iverilog -o tb_blink.vvp tb_blink.v blink.v
vvp tb_blink.vvp
gtkwave dump.vcd

📝 Notes

Installed Icarus Verilog for simulation

Installed GTKWave for waveform viewing


---

# 📘 `week1/day02_rtl_basics.md`

```markdown
# ⚡ Day 02 — RTL Basics  

✅ Learned the concept of RTL  
✅ Understood registers and data flow  



## 💻 Sample RTL Code
```verilog
module counter (
    input clk,
    input rst_n,
    output reg [3:0] q
);
always @(posedge clk or negedge rst_n) begin
    if (!rst_n) q <= 4'b0;
    else q <= q + 1;
end
endmodule




