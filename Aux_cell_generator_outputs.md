# AUX-CELL GENERATION BLOCK DIAGRAM

![WhatsApp Image 2022-11-04 at 11 14 47 AM](https://user-images.githubusercontent.com/62790565/199909816-7cfae85b-13d7-4abd-b9a3-9ea817d215b3.jpeg)

## Input of Aux-cell generator
- netlist.py
- lib.pyc
- pdk
- param-lef
- <design>.sp
  
## Outputs of Aux-cell generator
- .lef
- .v
- .gds
- .cdl
- .lib
  
Looking into .cdl and .lib file
### .cdl file
- .cdl is Circuit Description Language is a kind of netlist, a description of an electronic circuit. It is automatically generated from a circuit schematic of aux-cell.
- Layout vs Schematic (LVS) compares the design layout with the design schematic/netlist to tell if the design is functionally equivalent to schematic. For this, the connections are extracted from layout of the design by using a set of rules to convert the layout to connections. These connections are, then compared if they match with the connections of the netlist. If the connections match, the LVS is said to be clean. 
