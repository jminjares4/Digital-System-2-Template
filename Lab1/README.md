# Lab 1 XOR implemented with NAND gates :zap:

The purpose of this lab is to continue to become familiar with the implementation, testing and verification of  simple  circuits  using  a  computer-aided  design  tool.  In  addition,  you  will  learn  how  to  create  a schematic symbol and use instances of it to implement your design.

## Prelab
Using solely two-input NAND gates, implement a two-input XOR function in a modular manner.

**1)** First, create an inverter using a NAND gate and show resulting circuit.<br>
**2)** Then, create AND and OR gates using only NAND gates and the inverter module that you created in the first step. Show resulting circuit.<br>
**3)** Finally, using the AND, OR and the inverter modules created above, implement the XOR function in the form of sum-of-products. Note:  You should  not  use  De  Morgan’s  theorem by  simply  converting  AND-OR  network  to NAND-NAND network. This is not what you are requested to do.


## In lab session
**1)** Implement your modular design using Xilinx Schematic capture (You will need to create new 
schematic symbols)

**2)** Simulate your design and demonstrate proper behavior of your simulated waveforms to your 
TA

**3)** Remember to obtain screen images along the way to create your report (Schematics, 
simulation waveform)

```verilog
 module Xor_nand(
    input A,
    input B,
    output Out);

    //code

 endmodule
```
*Requirements:*

- [ ]  Schematic
- [ ]   Testbench
- [ ]   Simulation Waveform


## Authors:
* [**Jesus Minjares**](https://github.com/jminjares4)
    * Master of Science in Computer Engineering <br>
[![Outlook](https://img.shields.io/badge/Microsoft_Outlook-0078D4?style=for-the-badge&logo=microsoft-outlook&logoColor=white&style=flat)](mailto:jminjares4@miners.utep.edu) 
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white&style=flat)](https://www.linkedin.com/in/jesus-minjares-157a21195/) [![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white&style=flat)](https://github.com/jminjares4)
* [**Ismael Holguin**](https://github.com/iholguin6)
    * Master of Science in Computer Engineering <br>
[![Outlook](https://img.shields.io/badge/Microsoft_Outlook-0078D4?style=for-the-badge&logo=microsoft-outlook&logoColor=white&style=flat)](mailto:iholguin6@miners.utep.edu) 
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white&style=flat)](https://www.linkedin.com/in/ismael-holguin-5ab421224/) [![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white&style=flat)](https://github.com/iholguin6)
    
