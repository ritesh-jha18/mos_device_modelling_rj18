#EE5341: Level-3 MOSFET Modeling Project

This repository contains the project work for EE5341: MOS Device Modeling. The project implements a Level-3 DC MOSFET model in Verilog-A for NMOS and PMOS devices and simulates a CMOS inverter. It also explores the effect of channel-length modulation (λ) on device and inverter characteristics.

Project Overview

Implemented Level-3 MOSFET models for n-channel and p-channel transistors in Verilog-A.

Studied output characteristics (ID vs VDS) and transfer characteristics (ID vs VGS) for both NMOS and PMOS.

Analyzed CMOS inverter behavior under varying λ values.

Compared device and inverter performance for λ = 0, 0.01, and 0.1 V⁻¹.

Validated the effect of channel-length modulation on saturation current, output resistance, and inverter voltage transfer characteristics.

Folder Structure
.
├── VerilogA/
│   ├── level3_mosfet.va      # Generic Level-3 NMOS/PMOS model
│   └── cmos_inverter.va      # CMOS inverter example using the above model
├── Schematics/
│   ├── nmos_circuit.png      # NMOS simulation schematic
│   ├── pmos_circuit.png      # PMOS simulation schematic
│   └── cmos_inverter.png     # CMOS inverter schematic
├── Plots/
│   ├── nmos_id_vds.png       # Output characteristics of NMOS
│   ├── nmos_id_vgs.png       # Transfer characteristics of NMOS
│   ├── pmos_id_vds.png       # Output characteristics of PMOS
│   ├── pmos_id_vgs.png       # Transfer characteristics of PMOS
│   └── cmos_vtc.png          # CMOS inverter voltage transfer curve
├── README.md                 # Project description
└── Report.pdf                # Full project report with results and conclusions

How to Run Simulations

Open your Cadence Virtuoso or any compatible Verilog-A simulator.

Instantiate the level3_mosfet module for NMOS or PMOS:

level3_mosfet n1(drain, gate, source, bulk);
defparam n1.TYPE = "NMOS";
defparam n1.W = 5e-6;
defparam n1.L = 0.2e-6;
defparam n1.VTO = 0.4;
defparam n1.KP = 5e-4;
defparam n1.LAMBDA = 0.1;


Sweep VDS or VGS for output/transfer characteristics.

For CMOS inverter, instantiate one NMOS and one PMOS and sweep the input voltage:

level3_mosfet nmos(d, vin, gnd, gnd);
level3_mosfet pmos(d, vin, vdd, vdd);


Collect plots for ID vs VDS, ID vs VGS, and Vout vs Vin.

Key Observations

Increasing λ introduces finite output conductance in saturation, affecting drain current.

CMOS inverter gain decreases slightly with higher λ due to reduced output resistance.

Level-3 MOSFET models capture body effect, channel-length modulation, and basic saturation behavior accurately.

Technologies Used

Verilog-A for device modeling

Cadence Virtuoso / Spectre for simulation

MATLAB / Python for plotting (optional)

LaTeX / Overleaf for project report

Author

Ritesh Jha
EE5341: MOS Device Modeling – Project Assignment
Indian Institute of Technology Madras
