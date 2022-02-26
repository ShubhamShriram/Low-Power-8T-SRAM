
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



## Spice Netlist 

Please refer to the netlist here. [Netlist.txt](https://github.com/ShubhamShriram/SRAM_8T/files/8146363/Netlist.txt)


![Netlist 1](https://user-images.githubusercontent.com/100414911/155839261-98a37259-d984-4217-8129-d33e63187512.GIF)

![Netlist 2](https://user-images.githubusercontent.com/100414911/155839264-16556b50-7eec-4b55-be05-9cffe215a66e.GIF)

![Netlist 3](https://user-images.githubusercontent.com/100414911/155839267-a134fa9a-2f50-445a-adf9-59c97366b50a.GIF)


## Acknowledgement


- Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd. - kunalpghosh@gmail.com
- Chinmay panda, IIT Hyderabad
- Sameer Durgoji, NIT Karnataka
- Synopsys Team/Company
## References

1. Nahid Rahman and B. P. Singh. Design and Verification of Low Power SRAM using 8T SRAM Cell Approach

2. Farshad Moradi, Mohammad Tohidi, Behzad Zeinali, Jens K. Madsen. 8T-SRAM cell with Improved Read and Write Margins in 65 nm CMOS Technology
