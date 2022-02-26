
# Low Power SRAM using 8T SRAM Cell Approach 





## Appendix

1. Abstract

2. Synopsys Custom Compiler Tool Details

3. Circuit Details

4. Circuit Design

5. Waveforms

6. Spice Netlist

7. Acknowledgement

8. References


## Abstract

This paper proposes the implementation of a 1 bit low power 8T SRAM cell. One of the major advantage of this design is, there is no requirement of a precharge circuit as required in the traditional 8T SRAM cell and a sense amplifier circuit as required in 6T SRAM cell because the stored value is directly passed through transmission gate. This SRAM cell is designed using the Synopsys Customer Compliler with 28nm CMOS Technology as a part of Cloud Based Analog IC Design Hackathon
## Synopsys Custom Compiler

![Customer Compiler](https://user-images.githubusercontent.com/100414911/155836981-66449787-d7a3-4794-84f2-b5f18002354b.gif)



## Circuit Details



![Schematics](https://user-images.githubusercontent.com/100414911/155837802-caf58183-4f64-45d7-94bb-ebb59d049913.GIF)


![Schematics symbol](https://user-images.githubusercontent.com/100414911/155837836-88685e9e-78d4-456a-904e-6d60e34e1723.GIF)


![WLR BL Q RBL Testbench](https://user-images.githubusercontent.com/100414911/155837740-15a0e1ce-9e66-443b-a2cc-043f549ff3e5.GIF)


![WLR BL Q RBL](https://user-images.githubusercontent.com/100414911/155837696-99b481a4-897b-4252-bb77-179e035824c7.gif)


![WLR BLB QB RBL](https://user-images.githubusercontent.com/100414911/155838021-0195590d-4a9a-49c1-b128-0e75a65fd172.png)



## Netlist 


*  Generated for: PrimeSim
*  Design library name: cp_lib1
*  Design cell name: SRAM_TB
*  Design view name: schematic
.lib 'saed32nm.lib' TT

*Custom Compiler Version S-2021.09
*Fri Feb 25 07:10:36 2022

.global gnd! vdd!
********************************************************************************
* Library          : cp_lib1
* Cell             : SRAM
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
.subckt sram bl blb q qb rbl rwl rwlb vcc vssa wlr vt_bulk_n_gnd! vt_bulk_p_vdd!
xm5 q rwl rbl vt_bulk_n_gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm4 q wlr bl vt_bulk_n_gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm2 blb wlr qb vt_bulk_n_gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm1 qb q vssa vt_bulk_n_gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm0 q qb vssa vt_bulk_n_gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm8 q rwlb rbl vt_bulk_p_vdd! p105 w=0.1u l=0.03u nf=1 m=1
xm7 qb q vcc vt_bulk_p_vdd! p105 w=0.1u l=0.03u nf=1 m=1
xm6 q qb vcc vt_bulk_p_vdd! p105 w=0.1u l=0.03u nf=1 m=1
.ends sram

********************************************************************************
* Library          : cp_lib1
* Cell             : SRAM_TB
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
v33 wlr gnd! dc=0 pulse ( 1 0 0 0.1u 0.1u 10u 20u )
v17 blb gnd! dc=0 pulse ( 0 1 0 0.1u 0.1u 5u 10u )
v16 bl gnd! dc=0 pulse ( 01 0 0 0.1u 0.1u 5u 10u )
v41 rwlb gnd! dc=1
v42 rwl gnd! dc=1
v11 net43 gnd! dc=1
xi38 bl blb q qb rbl rwl rwlb net43 gnd! wlr gnd! vdd! sram








.tran '1u' '50u' name=tran

.option primesim_remove_probe_prefix = 0
.probe v(*) i(*) level=1
.probe tran v(bl) v(blb) v(q) v(qb) v(rbl) v(wlr)

.temp 25



.option primesim_output=wdf


.option parhier = LOCAL






.end

## Acknowledgement


- Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd. - kunalpghosh@gmail.com
- Chinmay panda, IIT Hyderabad
- Sameer Durgoji, NIT Karnataka
- Synopsys Team/Company
## References

1. Nahid Rahman and B. P. Singh. Design and Verification of Low Power SRAM using 8T SRAM Cell Approach

2. Farshad Moradi, Mohammad Tohidi, Behzad Zeinali, Jens K. Madsen. 8T-SRAM cell with Improved Read and Write Margins in 65 nm CMOS Technology
