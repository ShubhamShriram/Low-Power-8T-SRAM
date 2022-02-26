
# Low Power SRAM using 8T SRAM Cell Approach 





## Table of Content

### - Abstract

### - Synopsys Custom Compiler Tool

### - Circuit Design

### - Circuit Schematics and Symbol

### - Testbench setup

### - Waveforms

### - Spice Netlist

### - Author

### - Acknowledgement

### - References




## Abstract

This paper proposes the implementation of a 1 bit low power 8T SRAM cell. One of the major advantage of this design is, there is no requirement of a precharge circuit as required in the traditional 8T SRAM cell and a sense amplifier circuit as required in 6T SRAM cell because the stored value is directly passed through transmission gate. This SRAM cell is designed using the Synopsys Customer Compliler with 28nm CMOS Technology as a part of Cloud Based Analog IC Design Hackathon

## Synopsys Custom Compiler Tool

##### Custome Compiler:
Custom Compiler™ is a fresh, modern solution for full-custom analog, custom digital, and mixed-signal integrated circuit (IC) design. As the heart of the Synopsys Custom Design Platform, Custom Compiler provides design entry, simulation management and analysis, and custom layout editing features. Designed to handle the most challenging requirements of FinFET process technologies, it delivers industry-leading productivity, performance, and ease-of-use while remaining easy to adopt for users of legacy tools.

![Customer Compiler](https://user-images.githubusercontent.com/100414911/155836981-66449787-d7a3-4794-84f2-b5f18002354b.gif)

##### • Synopsys Primewave:
PrimeWave™ Design Environment is a comprehensive and flexible environment for simulation setup and analysis of analog, RF, mixed-signal design, custom-digital and memory designs within the Synopsys Custom Design Platform. This tool helped in various types of simulations of the above designed circuit.

##### • Synopsys 28nm PDK:
The Synopsys 28nm Process Design Kit(PDK) was used in creation and simulation of the above designed circuit.



## Circuit Design

##### Conventional 6T SRAM
The conventional 6T SRAM cell is vulnerable to noise during the read operation,
which when coupled with transistor mismatch( caused due to
the process variation) could result in functional read failures.
This cell shows poor stability at very small feature sizes, the
hold and read static noise margins are small for robust
operation.  The common approach to meet the
objective of low power design is to add more transistors to the
original 6T cell. 

##### Existing 8T SRAM
An 8T cell can be found to solve the problem.
One of the major advantage of 8T SRAM cell is that data nodes are fully decoupled from read access and due to this the
read stability is significantly improved. This cell employs two more transistors to access the read
bitline. The transistor configuration (i.e. M1 through M6) is
identical to a conventional 6T SRAM cell. Two additional
transistors M7 and M8 (thus yielding an 8T cell design) are
employed in to reduce the leakage current.
To overcome the problem of data storage destruction during
the read operation, an 8T-cell implementation was proposed, for which separate read/write bit and word signal lines
are used as shown in Figure, to separate the data retention
element and the data output element. In turn, the cell
implementation provides a read-disturb-free operation.

Write access to the cell occurs through the write access
transistors and from the write bitlines, BL and BLB. Read
access to the cell is through the read access transistor and
controlled by the read wordline, RWL. The read bitline, RBL,
is precharged prior to the read access. The wordline for read is
also distinct from the write wordline. By doing this the worsecase stability condition encountered previously in a 6T SRAM
cell, is avoided and high read stability is retained.
However, for the 8T structure, the read bitline leakage is
greater, especially in deep submicron/nano ranges. When the
column for Read (RBL) is not accessed, the leakage current
through M7 may cause a severe voltage drop at the read
bitline, leading to large Power dissipation, thus error may
appear at the output. So we proposed another 8T SRAM Cell
which can solve such kind of problems. 

![Reference SRAM 8T traditional](https://user-images.githubusercontent.com/100414911/155842124-4ab1b5f4-fa35-458d-bd45-391e763c3e9f.GIF)


##### Proposed 8T SRAM

In this project, I propose a single ended 8T SRAM design as
shown in Figure, that enhances data stability by improving the
Read Static Noise Margin and also reduces the Power
Consumption as a transmission gate is used for
Read purpose. The additional signal RWLB is an inversion
signal of read word line (RWL). It controls the additional
transistor M7 of the transmission gate. While the RWL and
RWLB are asserted and once the transmission gate is ON, a
stored node is connected to RBL. Thus, a stored value at Q is
being transferred to or read through RBL. One of the major
advantage of this design is that it is not necessary to prepare a
pre-charge circuit as required in prior 8T SRAM cell and a
sense amplifier circuit as required in 6T SRAM cell because
the stored value is directly passed through transmission gate.
A charge/discharge power on the RBL is consumed only when
the RBL is changed. Consequently, no power is dissipated on
the RBL if an upcoming data is the same as the previous state.
The design reduces a bit line power in both cases that the
consecutive ‘0’s and consecutive ‘1’s are read out.

![Reference SRAM 8T Cell](https://user-images.githubusercontent.com/100414911/155839648-db92888c-6a97-45bd-aa28-784edc5f4bc2.gif)


## Circuit Schematics and Symbol

##### Proposed 8T SRAM Schematics 
![Schematics](https://user-images.githubusercontent.com/100414911/155837802-caf58183-4f64-45d7-94bb-ebb59d049913.GIF)


##### 8T SRAM Symbol 
![Schematics symbol](https://user-images.githubusercontent.com/100414911/155837836-88685e9e-78d4-456a-904e-6d60e34e1723.GIF)

## Testbench Setup 

##### Testbench Setup in Synopsys

![WLR BL Q RBL Testbench](https://user-images.githubusercontent.com/100414911/155837740-15a0e1ce-9e66-443b-a2cc-043f549ff3e5.GIF)

## Waveforms 

###### Transient analysis of the SRAM cell.
When WLR line is active, the BL and BLB inputs are passed to the CMOS inverter cell and hence we can observe the basic working of the SRAM cell with respect to time. The output value Q changes according to the input BL only when the Write line WLR is active and rest of the time cell it is at static or hold state. Also the exact data which is at Q is transmitted to RBL.
![FInal WLR BL Q RBL](https://user-images.githubusercontent.com/100414911/155843114-800285b4-8dd5-4d8f-b2d5-651145d70729.gif)
Similarly, the output value QB changes according to the input BLB when the Write line WLR is active and rest of the time cell it is at static or hold state. Also the inverted data of QB appears at RBL.

![Final WLR BLB QB RBL ](https://user-images.githubusercontent.com/100414911/155843306-ff23469d-c903-47e5-83ec-8f2693b017de.gif)


## Spice Netlist 
Please refer to the netlist here. [Netlist.txt](https://github.com/ShubhamShriram/SRAM_8T/files/8146363/Netlist.txt)


![Netlist 1](https://user-images.githubusercontent.com/100414911/155839261-98a37259-d984-4217-8129-d33e63187512.GIF)

![Netlist 2](https://user-images.githubusercontent.com/100414911/155839264-16556b50-7eec-4b55-be05-9cffe215a66e.GIF)

![Netlist 3](https://user-images.githubusercontent.com/100414911/155839267-a134fa9a-2f50-445a-adf9-59c97366b50a.GIF)

## Author 

- Shubham Venkatesh Shriram, BE(ECE), Working at Applied Materials

## Acknowledgement


- Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd. - kunalpghosh@gmail.com
- Chinmay panda, IIT Hyderabad
- Sameer Durgoji, NIT Karnataka
- Synopsys Team/Company
## References

1. Nahid Rahman and B. P. Singh. Design and Verification of Low Power SRAM using 8T SRAM Cell Approach

2. Farshad Moradi, Mohammad Tohidi, Behzad Zeinali, Jens K. Madsen. 8T-SRAM cell with Improved Read and Write Margins in 65 nm CMOS Technology

