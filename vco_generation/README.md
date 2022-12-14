# AUX_CELL GENERATION
Auxiliary cells, similar to standard cells in digital design, are one of the building blocks for the analog generators. They have simple analog functionality usually associated with the structure of the auxiliary cell.“ALIGN” tool is used to .lef and .gds for auxiliary cells.

## ALIGN Tool
ALIGN (Analog Layout, Intelligently Generated from Netlists) is an open source automatic layout generator for analog circuits jointly developed under the DARPA IDEA program by the University of Minnesota, Texas A&M University, and Intel Corporation.The goal of ALIGN is to automatically translate an unannotated (or partially annotated) SPICE netlist of an analog circuit to a GDSII layout. 
</br>ALIGN flow of generating .gds and .lef files from spice netlist

<img width="285" alt="align" src="https://user-images.githubusercontent.com/62790565/206875850-9ba53dee-c17f-49bf-baa0-a672e5ccae83.png">

### ALIGN Installation steps
**Prerequisites**
- gcc >= 6.1.0 (For C++14 support)
- python >= 3.7

Type the following commands in terminal to install ALIGN
```
export CC=/usr/bin/gcc
export CXX=/usr/bin/g++
git clone https://github.com/ALIGN-analoglayout/ALIGN-public
cd ALIGN-public

#Create a Python virtualenv
python -m venv general
source general/bin/activate
python -m pip install pip --upgrade

# Install ALIGN as a USER
pip install -v .
```
Making ALIGN portable sky130 pdk
```
git clone https://github.com/ALIGN-analoglayout/ALIGN-pdk-sky130
```
move SKY130_PDK folder from ALIGN-pdk-sky130 to pdks folder of cloned ALIGN-public directory.

## PLL generator
A Phase locked loop(PLL) mainly consists of the following four blocks:-
1. Phase Detector(PD)
2. Charge Pump (CP)
3. Voltage Controlled Oscillator (VCO)
4. Frequency Divider (FD)

## Voltage Controlled Oscillator (VCO)
Voltage Controlled Oscillator generates(VCO) a DC signal, the amplitude of which is proportional to the amplitude of output of Charge Pump Control Signal. Here the adjustment in the output frequency/phase of VCO is made until it shows equivalency with the input signal frequency/phase. The VCO is contructed using two current mirrors and a ring Oscillator which makes it a Analog block. The control signal is used as an input to these current source(mirrors) to control the current supply which in turn control the delay of the circuit. By controlling the delay we are basically controlling the frequency of the Oscillator which makes it frequency flexible.

<img width="568" alt="vcocir" src="https://user-images.githubusercontent.com/62790565/206875662-10ea9781-dded-42ce-856c-cb0d80ff97af.png">


## Generating .gds and .lef files for VCO

Open terminal and give the following commands to generate .gds and .lef files

![Screenshot from 2022-12-13 18-35-56](https://user-images.githubusercontent.com/62790565/207328132-b0a40926-34ff-46db-8073-35dd5d9ed4d2.png)

Give the following command to view .gds file

![Screenshot from 2022-12-13 18-36-42](https://user-images.githubusercontent.com/62790565/207328292-80aea1cc-55b5-4cf0-b279-5ce7d4ef2d56.png)

### KLayout view of VCO .gds file

![Screenshot from 2022-12-11 10-52-34](https://user-images.githubusercontent.com/62790565/207322878-f4bc45fc-6aac-4c83-b865-ba3ce0301e19.png)

## FUTURE WORK
1. Pre-layout simulation is not matching with Post-layout simulation.
2. ALIGN PDK are been used in the design, this encounters an issue at OpenFasoc.

# Contributer
- Banda Anusha

# Acknowlegement
- Kunal Ghosh, Director, VSD Corp. Pvt. Ltd.
- Nickson Jose, VLSI Engineer, VSD Corp. Pvt. Ltd.
- Madhav Rao, Professor, IIIT-Bangalore.
- Nanditha Rao, Professor, IIIT-Bangalore.

# Contact Information
- Banda Anusha, Postgraduate Student, International Institute of Information Technology, Bangalore Banda.Anusha@iiitb.ac.in
- Kunal Ghosh, Director, VSD Corp. Pvt. Ltd. kunalghosh@gmail.com
- Madhav Rao, Professor, IIIT-Bangalore. mr@iiitb.ac.in
- Nanditha Rao, Professor, IIIT-Bangalore. nanditha.rao@iiitb.ac.in

# References
- https://fasoc.engin.umich.edu/
- https://github.com/idea-fasoc/OpenFASOC/tree/main/openfasoc/generators/temp-sense-gen
- https://align-analoglayout.github.io/ALIGN-public/notes/flow.html
- https://github.com/drvasanthi/OpenFASOC.git
- https://github.com/mahati-basavaraju/openFasoc_Flow




