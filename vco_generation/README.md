# AUX_CELL GENERATION
Auxiliary cells, similar to standard cells in digital design, are one of the building blocks for the analog generators. They have simple analog functionality usually associated with the structure of the auxiliary cell.“ALIGN” tool is used to .lef and .gds for auxiliary cells.

<img width="285" alt="align" src="https://user-images.githubusercontent.com/62790565/206875850-9ba53dee-c17f-49bf-baa0-a672e5ccae83.png">

## PLL generator
A Phase locked loop(PLL) mainly consists of the following four blocks:-
1. Phase Detector(PD)
2. Charge Pump (CP)
3. Voltage Controlled Oscillator (VCO)
4. Frequency Divider (FD)

## Voltage Controlled Oscillator (VCO)
Voltage Controlled Oscillator generates(VCO) a DC signal, the amplitude of which is proportional to the amplitude of output of Charge Pump Control Signal. Here the adjustment in the output frequency/phase of VCO is made until it shows equivalency with the input signal frequency/phase. The VCO is contructed using two current mirrors and a ring Oscillator which makes it a Analog block. The control signal is used as an input to these current source(mirrors) to control the current supply which in turn control the delay of the circuit. By controlling the delay we are basically controlling the frequency of the Oscillator which makes it frequency flexible.

<img width="568" alt="vcocir" src="https://user-images.githubusercontent.com/62790565/206875662-10ea9781-dded-42ce-856c-cb0d80ff97af.png">

