### Previous statge : https://github.com/drvasanthi/AUX_CELL.git

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
  
#### Looking into .cdl and .lib file
### .cdl file
- .cdl is Circuit Description Language is a kind of netlist, a description of an electronic circuit. It is automatically generated from a circuit schematic of aux-cell.
- Layout vs Schematic (LVS) compares the design layout with the design schematic/netlist to tell if the design is functionally equivalent to schematic. For this, the connections are extracted from layout of the design by using a set of rules to convert the layout to connections. These connections are, then compared if they match with the connections of the netlist. If the connections match, the LVS is said to be clean. 
- .cdl files are present in the folder (OpenFASOC/openfasoc/generators/design_name/blocks/sky130hs/spice/auxcell.cdl)  and it is modified so that a spice file is produced which is able to pass LVS. The code for this is present in https://github.com/idea-fasoc/OpenFASOC/blob/main/openfasoc/generators/temp-sense-gen/flow/util/openfasoc/cdl_parser.py 
  
 ### .lib file
- .lib files (auxillary library files) are in the path  aux_lib = genDir + ""blocks/"" + platform and are used for verilog generation code for which is found in directory OpenFASOC/openfasoc/generators/tools 

 ## LVS
 - Converting GDS to spice netlist
  open magic tcl window. Type the following commands to convert gds to spice netlist.
  ```
 % extract all
 % ext2spice hierarchy on
 % ext2spice scale off
 % ext2spice
  ```
  - Comparing spice netlists
  Open terminal and type the folowing command to netgen tcl window
  ```
  $ netgen
  ```
  Type the following command to compare netlists
  ```
 % lvs original.spice netlist_extracted_from _gds.spice
  ```
  
### LVS report
  
  ![lvs_report](https://user-images.githubusercontent.com/62790565/200115230-c612df93-898d-4aef-9daf-2e845a4ce8a0.jpg)
  
### Next Stage : https://github.com/mahati-basavaraju/openFasoc_Flow 
