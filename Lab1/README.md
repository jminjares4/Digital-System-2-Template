# Lab 1 XOR implemented with NAND gates :zap:

The purpose of this lab is to continue to become familiar with the implementation, testing and verification of  simple  circuits  using  a  computer-aided  design  tool.  In  addition,  you  will  learn  how  to  create  a schematic symbol and use instances of it to implement your design.

## Prelab
Using solely two-input NAND gates, implement a two-input XOR function in a modular manner.

**1)** First, create an inverter using a NAND gate and show resulting circuit.<br>
**2)** Then, create AND and OR gates using only NAND gates and the inverter module that you created in the first step. Show resulting circuit.<br>
**3)** Finally, using the AND, OR and the inverter modules created above, implement the XOR function in the form of sum-of-products. Note:  You should  not  use  De  Morgan’s  theorem by  simply  converting  AND-OR  network  to NAND-NAND network. This is not what you are requested to do.

```verilog
 module Xor_nand(
    input A,
    input B,
    output Out);
    
    //create a wire to store inverter A
    wire a_inv_out;
    Inverter first_inv(.A(A), .B(A), .Out(a_inv_out));
    //create a wire to store inverter B
    wire b_inv_out;
    Inverter second_inv(.A(B),.B(B), .Out(b_inv_out));
    //create wire to store Nand A
    wire a_nand_out;
    Nand a_nand(.A(A),.B(b_inv_out), .Out(a_nand_out));
    //create wire to store Nand B
    wire b_nand_out;
    Nand b_nand(.A(B), .B(a_inv_out), .Out(b_nand_out));
    //create an instance of Nand and pass the outputs of Nand A, Nand B and store in Out
    Nand c_nand(.A(a_nand_out), .B(b_nand_out), .Out(Out));
    
 endmodule
```

## Authors:
* [**Jesus Minjares**](https://github.com/jminjares4)
    * Master of Science in Computer Engineering <br>
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white&style=flat)](https://www.linkedin.com/in/jesus-minjares-157a21195/) [![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white&style=flat)](https://github.com/jminjares4)
* [**Ismael Holguin**](https://github.com/iholguin6)
    * Master of Science in Computer Engineering <br>
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white&style=flat)](https://www.linkedin.com/in/ismael-holguin-5ab421224/) [![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white&style=flat)](https://github.com/iholguin6)
    
   