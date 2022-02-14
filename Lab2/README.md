# Lab 2 Hexadecimal Full Adder :zap:
The purpose of this lab is to review and become familiar with the design and testing of 
combinational circuits using modular design (block symbols) in a computer-aided design tool. 
The circuit is to be designed and simulated in XilinxVivado environment. 

## Prelab
Using solely two-input AND gates and OR gates, implement a Hexadecimal Adder in a 
modular manner.

**1)** First, create a binary Full-adder module: 
        Write down the binary full adder truth table
        Demonstrate you know how to use K-Maps to derive the SOP Boolean equations for Sum and Cout
        Implement the obtained equations using ONLY 2-input AND and OR gates. Show the resulting circuit. 
        
 **2)** Now, create the Hexadecimal adder
        Using a block diagram representation of your full adder (corresponding to step 1 above) show how to connect 
        enough instances of it to create a Hexadecimal adder (Circuit that is able to add one hexadecimal digit to another hexadecimal digit). 
        Show the resulting circuit
       
# Full-adder Module
```verilog
//FullAdder module of two bits 
module FullAdder(input A, input B, input C, output Sum, output Cout);

    //create wires to store and and or outputs
    wire a01,a02,a03,a04;
    wire a11,a12,a13,a14;
    wire o01, o02;
    //instantiate AND and OR gates for the SUM
    And And1(.A(~A),.B(~B),.Out(a01)); 
    And And2(.A(~A),.B(B),.Out(a02));
    And And3(.A(A),.B(B), .Out(a03));
    And And4(.A(A),.B(~B), .Out(a04));
    And And5(.A(a01),.B(C),.Out(a11));
    And And6(.A(a02),.B(~C),.Out(a12));
    And And7(.A(a03),.B(C),.Out(a13));
    And And8(.A(a04),.B(~C),.Out(a14));
    Or Or1(.A(a11),.B(a12),.Out(o01));
    Or Or2(.A(a13),.B(a14),.Out(o02));
    Or Or3(.A(o01),.B(o02),.Out(Sum));
    
    // instantiate AND and OR gates for the Cout
    wire c1,c2,c3,c4;
    And And9(.A(A),.B(C),.Out(c1));
    And And10(.A(A),.B(B),.Out(c2));
    And And11(.A(B),.B(C),.Out(c3));
    Or Or4(.A(c1),.B(c2),.Out(c4));
    Or Or5(.A(c4),.B(c3),.Out(Cout));
endmodule
```

# Hexadecimal Adder
```verilog
//Hexadecimal adder with two 4 bits inputs and 4 bits sum output 
module HexAdder(input [3:0]A, input[3:0]B, input C, output [3:0]Sum, output Cout);
    //create wire to store Cin output
    wire co, c1, c2;
    //instantiate Fulll-adder modules
    FullAdder f1(.A(A[0]),.B(B[0]),.C(C),.Sum(Sum[0]),.Cout(co));
    FullAdder f2(.A(A[1]),.B(B[1]),.C(co),.Sum(Sum[1]),.Cout(c1));
    FullAdder f3(.A(A[2]),.B(B[2]),.C(c1),.Sum(Sum[2]),.Cout(c2));
    FullAdder f4(.A(A[3]),.B(B[3]),.C(c2),.Sum(Sum[3]),.Cout(Cout));
    
endmodule  
```
## Authors:
* [**Jesus Minjares**](https://github.com/jminjares4)
    * Master of Science in Computer Engineering <br>
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white&style=flat)](https://www.linkedin.com/in/jesus-minjares-157a21195/) [![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white&style=flat)](https://github.com/jminjares4)
* [**Ismael Holguin**](https://github.com/iholguin6)
    * Master of Science in Computer Engineering <br>
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white&style=flat)](https://www.linkedin.com/in/ismael-holguin-5ab421224/) [![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white&style=flat)](https://github.com/iholguin6)
    