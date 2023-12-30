# EXPNO:4 Implementation-of-Half-subtractor-and-Full-subtractor-circuit
# AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
Hardware – PCs, Cyclone II , USB flasher
# Software:
Quartus prime

## Theory:
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

# Half Subtractor Full Subtractor
# Half Subtractor:
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

# PROGRAM:
```
DESIGNED BY: Harsshitha lakshmanan
REGISTER NUMBER: 212223230075

module halfsub(a,b,borrow,diff);	                                          
input a,b;
output borrow,diff; 
assign borrow=~a&b;
assign diff=a^b; 
endmodule
```
# RTL Realization:
![image](https://github.com/harshulaxman/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/145686689/f6a27a06-8c05-4d54-9144-c8bf772db93b)

# Truth table:
![image](https://github.com/harshulaxman/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/145686689/3c3be2fd-4945-4056-b354-a5fa1c255bad)

# TIMING DIAGRAM:
![image](https://github.com/harshulaxman/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/145686689/574095cc-22be-49d7-87e3-b854487d1c6c)


## Full Subtractor:
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure



Write the detailed procedure here 


## Program:
```
Developed by: Harsshitha lakshmanan
RegisterNumber: 212223230075

module fullsub(a,b,bin,borrow,diff);	                                             
input a,b,bin;
output diff,borrow;
assign diff=(a^b)^bin;
assign borrow=((~a)&&bin)||(b&&bin)||((~a)&&b); 
endmodule

```
# RTL Realization:
![image](https://github.com/harshulaxman/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/145686689/b185e28e-f2cb-43a4-82d7-fe63dbd55737)

# Truthtable:
![image](https://github.com/harshulaxman/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/145686689/60b589bd-0c49-4481-922b-db2297ac4ccc)

# Timing Diagram:
![image](https://github.com/harshulaxman/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/145686689/e0e5b37f-9d5a-4e0c-9208-4794fcbdc874)

## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
