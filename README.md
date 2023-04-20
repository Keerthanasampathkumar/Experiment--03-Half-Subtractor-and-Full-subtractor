# Experiment--04-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

### Procedure

Write the detailed procedure here 

### Program:
### Half subtractor
module Ex04(a,b,difference,borrow);

inputs a,b;

outputs difference,borrow;

wire x;

xor(difference,a,b);

not(x,a);

and(borrow,x,b);

endmodule
### Full Subtractor
module Ex4(A,B,C,Difference,Borrow);

input A,B,C;

output Difference,Borrow;

wire p;

assign Difference=((A^B)^C);

not(p,A);

assign Borrow=((p&B)|(p&C)|(B&C));

endmodule
/*

Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.

Developed by: KEERTHANA S

RegisterNumber: 212222230066

*/

### Output:
### Truthtable
### HALF SUBTRACTOR
![t 1](https://user-images.githubusercontent.com/119477890/233269044-4f1565eb-a713-43dc-bf15-bdd2ffb0c892.png)
### FULL SUBTRACTOR
![t 2](https://user-images.githubusercontent.com/119477890/233270420-7cbb66db-dc20-43c9-b646-5f16cf64b1a2.png)
### RTL realization
### HALF SUBTRACTOR
![f 1](https://user-images.githubusercontent.com/119477890/233267095-323218e2-0133-4ef5-812b-f3f65ff5d886.png)

### FULL SUBTRACTOR
![h 1](https://user-images.githubusercontent.com/119477890/233267232-598687d7-0ecc-4ef4-a713-f81c039d9ec6.png)

### Timing diagram 
### HALF SUBTRACTOR
![f 2](https://user-images.githubusercontent.com/119477890/233267490-5bf5d426-25d1-478c-bbef-73ef536c7d5b.png)
### FULL SUBTRACTOR
![h 2](https://user-images.githubusercontent.com/119477890/233267517-0785addb-a1bf-426f-bea6-dc279a972690.png)

### Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
