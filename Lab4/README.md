# Lab 4: Washing Machine Controller  :zap:
The purpose of lab is to complete an ASM design with MSI components for a Washing Machine controller. The design must be implemented using Xilinx ISE environment and verify operation on ISim simulator.

## Prelab
  Submit the following 3 items:
  
  **1)** Based on provided *Block Diagram, Circuit Diagram and final ASM Chart*, specify **contents of the ROM** table 
  
  **2)** Specify the contents of the full Programming table.
  
  **3)** **Submit your rom_controller Verilog module**, using the values obtained in the previous step. 

## In Lab Session (50%)
**1.** Generate a Xilinx Project using modular design to implement your ASM 
 
**2**  Generate Verilog test fixture and carefully set the appropriate 
        conditions so it goes through all the states (including stopping the process 
        at one state to open the washer for a moment and resume operation) 


**3.** Arrange I/O in meaningful order. Use different colors for waveforms in ISim. 

**4.** Verify and **demonstrate to TA the full washing machine cycle** (complete all state transitions shown in ASM chart)  

## Lab Description: Washing Machine Controller
The washing operation begins when the user turns ON the “start” button 
which makes signal YSTART=1. Once the process has started, the 
controller will assert the appropriate signals to fill the washer’s tub with 
either cold or hot water (selected by the user) depending on the **NHOT** 
input (**NHOT** is True when hot water is desired). The washer agitates 
the tub until a cycle timer (**NCTO**) indicates that the cycle is finished. 
The controller then drains the soapy water and fills the machine with 
cold water for the rinse cycle. The washer agitates again until the cycle 
timer indicates that the cycle is finished. The controller drains the rinse 
water and finally enters the spin cycle, spinning the clothes dry until the 
cycle timer indicates the end of the cycle. Assume that if you want to 
pause (halt) the washing process (example: user opens the door, check 
on clothes, etc), the **YSTART** button must be turned into the OFF 
position and in such case **the washer will hold the current state** until 
the start button is turned ON again to continue.

## Signal Definition
***INPUTS:***

**YSTART** – Active high, from user, when button is turned ON (set to 1) 
it means the user wants to start the washing process. When turned OFF 
(cleared to 0) it means the user wants to stop the process.

**NHOT** – Active low, from user, when user selects hot water this signal 
will be asserted (true), if false NHOT will be 1 and cold water will be 
used.

**YFULL** – Active high, from the washing machine’s tub sensor. When 
the tub is completely full a 1 is sent, otherwise it sends a 0

**NEMPTY** – Active low, from the washing machine’s tub sensor. When 
the tub is completely empty a 0 is sent, otherwise it sends a 1

**NCTO** – Active low, from the washing machine cycle timer. When the 
cycle is over (counter times out), the timer sends a 0, otherwise it sends 
a 1 until the completion of the cycle designated time.

***OUTPUTS:*** 

**LCOLDW** - Active low, assertion activates Cold water valve

**HWIN** - Active high, assertion causes pump to put water into tub

**HAGIT** - Active high, assertion agitates the tub

**HWOUT**-Active high, assertion causes pump to take water out of tub 

**LSPIN** -Active low, assertion spins the motors for drying clothes 

**HBELL**-Active high, assertion rings a bell to indicate washing is completed

  *Find the corresponding final ASM Chart and Circuit Diagram in the following pages


## I ASM Chart
<img src="ASM_flowchart.png">

## II Schematic
<img src="Schematic.png">

# D-Flip-Flop (DFF) Module
```verilog
module DFF(input D, input clk, output reg Q);
    //code
endmodule
```
# INVERTER Module
```verilog
module INV(
    input A,
    output B
    );
    //code
endmodule
```
# 3-Bit DFF
```verilog
module threeBitReg(
        input [2:0]D,
        input Clk,
        output [2:0]Q
    );
    //code
endmodule
```
# 2-Bit DFF
```verilog
module twoBitReg(
        input [1:0]D,
        input Clk,
        output [1:0]Q
    );
  //code
endmodule
  
```
# Generic  4-BIT Mux
```verilog
module genMUX(
    input [1:0]S,
    input A, B, C, D,
    output Out
    );
// code    
endmodule
```
# Mux 
```verilog
module MUX(
    input [1:0]S,
    input YFULL, NCTO, NEMPTY,
    output Out
    );
  //code
endmodule 
```
# Generic Decoder
```verilog
  module genDECODER(
    input [1:0]Code,
    output reg [3:0]Data
    );
    //code 
    endmodule
 
```
# Decoder 1
```verilog
  module DEC1(
    input [1:0]S,
    output HBELL, LCOLDW, HAGIT
    );
    //code
    endmodule
```
# Decoder 2
```verilog
  module DEC2(
    input [1:0]S,
    output LSPIN, HWOUT, HWIN
    );
    //code 
    endmodule
    
```
# ROM
```verilog 
  module ROM(
    input [5:0]A,
    output reg [8:0]D
    );
    //code
  endmodule
```
# ASM
```verilog
  module ASM(
    input YFULL, NCTO, NEMPTY, NHOT, YSTART, Clk,
    output HBELL, LCOLDW, HAGIT, LSPIN, HWOUT, HWIN
    );
    //code
    endmodule
    
```
*Requirements:*

- [ ]  Schematic
- [ ]   Testbench
- [ ]   Simulation Waveform


# Software Development
| **Software** | **Environment** |
| :---:    | :---:       |
| ![Vivado](https://img.shields.io/static/v1?label=&message=Xilinx+Vivado&color=black&logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAEAAAABACAMAAACdt4HsAAABQVBMVEVeYABkZgB1dwB3eQCFhwCLjQmcniHS1CnV1zjX2Ufa3Fbl55Lo6qHq7Kzr7Vrr7bDt77%2Fu8Gn196v8%2FrT%2B%2F8P%2F%2F33%2F%2F9f%2F%2F%2F%2BLjQna3Fbl55Ll55La3Fbl55La3FaLjQna3Fbl55La3FaIigbl55Ll55KLjQmFhwCfoSba3FbZ21Ll55Ll55La3Fbl55LU1jTa3Fbl55L%2F%2F3ra3Fbl55La3Fba3Fbl55KLjQna3Fbl55La3Fbl55La3Fba3Fba3Fbl55KLjQn4%2Bq%2BLjQna3Fbl55Ll55Ll55KLjQna3Fbl55KLjQn196vb3Vzl55Ll55Ll55La3FZxcwB0dgDa3Fba3FaLjQna3Fba3FaLjQna3Fbl55KKjAeLjQnr7Wbl55La3Fba3FZ8fgCFhwCIigSLjQnX2Ufa3Fbl55Ln6Z3o6qFUKg%2FmAAAAYnRSTlMAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAFCREVGBkgJSgoKS00NUFFRUVJSU1QUWFlZWVtcHl9fYGBgYWFiZObm5%2Bjr6%2BvtLe7u7u%2Fv8bLz9PX29vb3t%2Ff4%2Bfn5%2Bvr6%2B%2Fz99V9LS0AAAI%2BSURBVHjapdJlm9swDMDxZJ12TZxjZmZmvhszM7PnbN%2F%2FA8yt00dtJbdx%2FX9d%2FZ7IajDoWTAY1%2FYmdooCSi37Ae%2BU%2BuEFXCjdgQewq8rNtAxMKNMLRwBTlU49Ad1wS8A7hT1wA%2FAM2JYTgGfAvrsBeAbs0hGIFWnGF1BuwGtf4DYFJpyAcwrsOgFjFLhwAmIKvLfNRxroNrVyhqjYqYFCubAfnRc5gagzERoAU5XDnGGKA4qJqALQCXcosM5%2Bv2AA3ezPrwTYZ8YTwQML8lX%2FVj3wkR%2FngEdSvg27yf%2B5Zt6M88B9qYFCfxwP24FIL28DZKm3EJbOeWw5Q1RMrIDMAP0JpX4wZ8D1KTAkKwCERpghZ8BxCixIBMwSuks8Q%2BX2NuCGrAb0ElnfjYBfTwB8fgTMEqatDIhwnAGkrAVwCd2D8hnw8RlAUqDQEWXF0fAftYLrU2BIMkDQl5g627raujaftAsrsCAZ4MqAqJSIZPXf3%2FS6DTiSHBD04q9WU9PTeQ64JTkgwA84S6s6o8AXDsAFTtK67ozXAW8ZQC%2BA47TVpkAwwI5jDxsDZgFuHPu00QAoLfAwbdqJDXg5IO6luXo%2BxwG%2FP99M83aXA34tPc45fsavsHitR2yzA%2BSYLABXNSDE6LMc4xwAGaA7bDzOA4CAbuOT4z%2FxESBgYg66JoQNOAIKiNoH%2FTYihBVYAA7AB8VxHhgCAmCHZJwAAByA7U0LjAGAB2g8cB%2F8gEfgByyAD%2FBBToIXIAH8AM%2F%2BAwk%2BiPzFN%2BOgAAAAAElFTkSuQmCC%0A)| ![Verilog](https://img.shields.io/static/v1?label=&message=Verilog&color=blue&logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAMAAABEpIrGAAAABGdBTUEAALGPC%2FxhBQAAAAFzUkdCAK7OHOkAAAAgY0hSTQAAeiYAAICEAAD6AAAAgOgAAHUwAADqYAAAOpgAABdwnLpRPAAAAVZQTFRFAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA%2F%2F%2F%2FyxSZEQAAAHB0Uk5TACDmwgk%2F%2B5dpllk088FTmnVzaPnPE7MFkpCcQuEewAe4Tt%2FFG2zlqAiD5%2BReJ3eMiGAMNX6NhFAEPn96K2H%2BgQJNvb6nZL8OR7DDxkXZ2AooItfa1tW7b9zd4N5qGkaHexyJbR1cSmu3ErKPm1JyWFVY6tcAAAABYktHRHGvB1ziAAAACXBIWXMAAA7EAAAOxAGVKw4bAAABf0lEQVQ4y92TWVOCUBiGKbG00lJLshCLFrVNrFxTs0NpUma2mEtGubQv5%2F9f9R2QxqkB7%2FsuzjMcHjjD8L4UBTM0bKIB5pFRcmXBFgIrHqO0GZ%2BwEcGOJ8nVFHaogvNHMLumZwBO7GYAs9hDNufUFykz72K9yrs5WnnUCqtvoU9Y5JeWASur%2FgAguBaENeBf39Dub26FhPA2tbMbicbiVCIZSSaoeCwa2kv1hHQGYzhjH2fIGVaAlaI5gHZGGvcErApYFbAmZA8QEg%2B9zFEOcZ68z8EhzuHLezgk2rPk%2FnGBkyTJJCIFCNkANoRMknQiFU7hc9xYZzLFM%2Bz2USVRTyiely9sJQPhcpCQubrGOSOBjPhfBLpiJFQgYjc8X61Wa3W2QcAqaLBsDcA3buFvMs07WRbuUw92QW61y51uS251O%2BV2SxYem4wSiDAkqm4QmMGRGxhaLfZPerGH4tT%2FFue5rzhQvReleq9q9d7I5nuf0Cvvh1bez9%2Fl1an%2FF8E34yTzLFjpmLMAAAAldEVYdGRhdGU6Y3JlYXRlADIwMjAtMDItMDdUMTc6MjQ6NDUrMDA6MDDiWEe%2BAAAAJXRFWHRkYXRlOm1vZGlmeQAyMDIwLTAyLTA3VDE3OjI0OjQ1KzAwOjAwkwX%2FAgAAAEZ0RVh0c29mdHdhcmUASW1hZ2VNYWdpY2sgNi43LjgtOSAyMDE5LTAyLTAxIFExNiBodHRwOi8vd3d3LmltYWdlbWFnaWNrLm9yZ0F74sgAAAAYdEVYdFRodW1iOjpEb2N1bWVudDo6UGFnZXMAMaf%2Fuy8AAAAYdEVYdFRodW1iOjpJbWFnZTo6aGVpZ2h0ADUxMsDQUFEAAAAXdEVYdFRodW1iOjpJbWFnZTo6V2lkdGgANTEyHHwD3AAAABl0RVh0VGh1bWI6Ok1pbWV0eXBlAGltYWdlL3BuZz%2ByVk4AAAAXdEVYdFRodW1iOjpNVGltZQAxNTgxMDk2Mjg13VzE4wAAABN0RVh0VGh1bWI6OlNpemUANy41M0tCQs3klRUAAABDdEVYdFRodW1iOjpVUkkAZmlsZTovLy4vdXBsb2Fkcy81Ni9zWnp0MUtzLzIxNDgvdmVyaWxvZ19pY29uXzEzMTg5NC5wbmc%2BkF9GAAAAAElFTkSuQmCC)|

## Authors:
* [**Jesus Minjares**](https://github.com/jminjares4)
    * Master of Science in Computer Engineering <br>
[![Outlook](https://img.shields.io/badge/Microsoft_Outlook-0078D4?style=for-the-badge&logo=microsoft-outlook&logoColor=white&style=flat)](mailto:jminjares4@miners.utep.edu) 
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white&style=flat)](https://www.linkedin.com/in/jesusminjares/) [![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white&style=flat)](https://github.com/jminjares4)
* [**Ismael Holguin**](https://github.com/iholguin6)
    * Master of Science in Computer Engineering <br>
[![Outlook](https://img.shields.io/badge/Microsoft_Outlook-0078D4?style=for-the-badge&logo=microsoft-outlook&logoColor=white&style=flat)](mailto:iholguin6@miners.utep.edu) 
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white&style=flat)](https://www.linkedin.com/in/ismael-holguin/) [![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white&style=flat)](https://github.com/iholguin6)
