# Experiment--02-Implementation-of-combinational-logic
Implementation of combinational logic gates
 
## AIM:
To implement the given logic function verify its operation in Quartus using Verilog programming.
 F1= A’B’C’D’+AC’D’+B’CD’+A’BCD+BC’D
F2=xy’z+x’y’z+w’xy+wx’y+wxy
 
 
 
## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime


## Theory
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output. 

## Using NAND gates
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

## Logic Diagram

Using NOR gates
NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'
~~~
Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.
Developed by: PREMNATH.E
RegisterNumber: 212222050045
~~~
## Procedure
## Program:
~~~
PROGRAM 1:
module expfour(a,b,c,d,f);
input a,b,c,d;
output f;
wire f1,f2,f3;
assign f1 = (~c&~b&~a);
assign f2 = (~d&~c&~a);
assign f3 = (c&~(~b)&~a);
assign f= f1&~f2&~f3;
endmodule

PROGRAM 2:
module expfourtwo(a,b,c,d,f);
input a,b,c,d;
output f;
wire f1,f2,f3,f4;
assign f1 = c&(~b)&a;
assign f2 = d&(~c)&a;
assign f3 = c&(~b)&a;
assign f4 = ~(f1|f2|f3);
not(f,f4);
endmodule
~~~
## RTL realization:
FOR PROGRAM 1:
![RTL](https://user-images.githubusercontent.com/93427224/192571983-e832ee83-ea15-400f-ab7d-3d03038dcf24.png)

FOR PROGRAM 2:
![rtl](https://user-images.githubusercontent.com/93427224/192572382-9552b0b2-c3eb-4b98-90ae-7c1749581124.png)

## Output:
### TRUTH TABLE:
FOR PROGRAM 1:
![TRUTH](https://user-images.githubusercontent.com/93427224/192572747-c981f4d7-4efe-45a1-b530-e5f3a4f701c0.PNG)

FOR PROGRAM 2:
![truth](https://user-images.githubusercontent.com/93427224/192572783-8d8ec80c-dd31-482c-a1c6-d6070a4fafe6.PNG)

## RTL
## Timing Diagram:
### For program 1:
![timing](https://user-images.githubusercontent.com/93427224/192572942-43fa4a56-1bef-4d8e-a986-8c5fac1393a4.png)

### For program 2:
![TIMING](https://user-images.githubusercontent.com/93427224/192573051-03c9eab6-683b-4813-bd5a-c85e69e93cdc.png)

## Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
