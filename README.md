# Experiment--04-Implementation-of-combinational-logic-using-universal-gates
Implementation of combinational logic using universal-gates
 
## AIM:
To implement the given logic function using NAND and NOR gates and to verify its operation in Quartus using Verilog programming.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')' using NAND gate
F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR gate
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

## Procedure

Step 1: Create a project with required entities.
Step 2: Create a module along with respective file name.
Step 3: Run the respective programs for the given boolean equations.
Step 4: Run the module and get the respective RTL outputs.
Step 5: Create university program(VWF) for getting timing diagram.
Step 6: Give the respective inputs for timing diagram and obtain the results.





## Program:

'''Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.
Developed by: Mathiyazhagan.A
RegisterNumber:  22005215
'''

USING NAND OPERATION

module fourexp(A,B,C,D,F);  
input A,B,C,D;  
output F;  
wire P,Q,R;  
assign P = C&(~B)&(~A);  
assign Q = D&(~C)&(~A);  
assign R = (~C)&B&(~A);  
assign F = (~P&~Q&~R);  
endmodule 

USING NOR OPERATION

module fourexp(A,B,C,D,F);  
input A,B,C,D;  
output F;  
wire P,Q,R,S;  
assign P = C&(~B)&A;  
assign Q = D&(~C)&A;  
assign R = C&(~B)&A;  
assign S = ~(P|Q|R);  
assign F = ~S;  
endmodule 


## Output:

## RTL

FOR NAND
![nandrtl](https://user-images.githubusercontent.com/118787327/214537039-e79888a9-e50a-4cfb-8b20-a441e6e308bc.png)

FOR NOR

![norrtl](https://user-images.githubusercontent.com/118787327/214537214-cc0ca835-4db1-4645-8857-2584fcb7d63e.png)


## Timing Diagram

FOR NAND

![nandtd](https://user-images.githubusercontent.com/118787327/214537566-1b3d9136-3456-4bff-a83f-e73939330ee9.png)

FOR NOR
![nortd](https://user-images.githubusercontent.com/118787327/214537684-ba4d1874-2000-488a-af64-396275c63d67.png)

## Truth table

FOR NAND


![nandtt](https://user-images.githubusercontent.com/118787327/214538021-04e77eb2-26bf-4860-b47a-dfc6eb0344f3.png)




FOR NOR



![nortt](https://user-images.githubusercontent.com/118787327/214538096-59cae23c-9c52-4b8a-bbd5-c271e64319c8.png)


## Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
