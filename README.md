EE5341: Level-3 MOSFET Modeling Project

This repository contains the Level-3 MOSFET modeling project for EE5341. The project implements NMOS, PMOS, and a CMOS inverter using Verilog-A and analyzes the effect of channel-length modulation (λ) on device and circuit behavior.

🔹 Features

Generic Level-3 MOSFET Verilog-A module for NMOS and PMOS

Simulation of output characteristics (ID vs VDS) and transfer characteristics (ID vs VGS)

CMOS inverter analysis with input-output voltage characteristics

Sweep of channel-length modulation λ values: 0, 0.01, 0.1 V⁻¹

Demonstrates body effect and short-channel effects

📂 Repository Structure
.
├── VerilogA/
│   ├── level3_mosfet.va      # NMOS/PMOS Level-3 model
│   └── cmos_inverter.va      # CMOS inverter example
├── Schematics/
│   ├── nmos_circuit.png      
│   ├── pmos_circuit.png      
│   └── cmos_inverter.png     
├── Plots/
│   ├── nmos_id_vds.png       
│   ├── nmos_id_vgs.png       
│   ├── pmos_id_vds.png       
│   ├── pmos_id_vgs.png       
│   └── cmos_vtc.png          
├── Report.pdf                
└── README.md                 

⚡ How to Run

Open Cadence Virtuoso (or compatible Verilog-A simulator).

Instantiate the NMOS/PMOS module with desired parameters:

level3_mosfet n1(drain, gate, source, bulk);
defparam n1.TYPE = "NMOS";
defparam n1.W = 5e-6;
defparam n1.L = 0.2e-6;
defparam n1.VTO = 0.4;
defparam n1.KP = 5e-4;
defparam n1.LAMBDA = 0.1;


Sweep VDS for output characteristics or VGS for transfer characteristics.

For CMOS inverter, instantiate one NMOS and one PMOS and sweep the input voltage:

level3_mosfet nmos(d, vin, gnd, gnd);
level3_mosfet pmos(d, vin, vdd, vdd);


Export plots for ID vs VDS, ID vs VGS, and Vout vs Vin.

📈 Key Observations

Increasing λ increases drain current in saturation (finite output resistance).

CMOS inverter gain decreases slightly with higher λ, slightly affecting switching sharpness.

Level-3 MOSFET model captures body effect, channel-length modulation, and realistic saturation behavior.

🎬 Demo

Here is a visual example of the CMOS inverter simulation:

ID vs VDS and ID vs VGS plots are in the Plots/ folder.

🛠 Technologies Used

Verilog-A for device modeling

Cadence Virtuoso / Spectre for simulation

MATLAB / Python for plotting (optional)

LaTeX / Overleaf for project report

📝 Author

Ritesh Jha
EE5341: MOS Device Modeling – Project Assignment
Indian Institute of Technology Madras
