# EXP: BOOLEAN_FUNCTION_MINIMIZATION
# DATE : 3rd Oct 2024

**AIM:**

To implement the given logic function verify its operation in Quartus using Verilog programming.

F1= A’B’C’D’+AC’D’+B’CD’+A’BCD+BC’D 

F2=xy’z+x’y’z+w’xy+wx’y+wxy

**Equipment Required:**

Hardware – PCs, Cyclone II , USB flasher

**Software – Quartus prime**

**Theory**
~~~
Boolean Function Minimization is the process of reducing a Boolean expression to its simplest form without changing its functionality. This minimization reduces the number of gates and inputs required, optimizing circuit design.

Logic Gates: Fundamental building blocks like AND, OR, and NOT gates are used to implement Boolean expressions. Karnaugh Map (K-map): A graphical technique for minimizing Boolean expressions by grouping terms based on commonalities. The given Boolean functions can be minimized as follows:

F1 = A’B’C’D’ + AC’D’ + B’CD’ + A’BCD + BC’D The terms can be simplified using K-map techniques to reduce the complexity of the circuit. F2 = xy’z + x’y’z + w’xy + wx’y + wxy Similar simplification can be done for this function to reduce the gate count. The resulting minimized expressions are implemented using Verilog HDL and simulated on the Quartus Prime tool. The outputs can then be verified on an FPGA board (e.g., Cyclone II).
~~~
**Logic Diagram**

![396449093-8db62afb-ea43-47ce-85af-50605d210908](https://github.com/user-attachments/assets/0bca6b76-8d38-4ed9-9910-bf1739594cdf)

**Truth Table**
![373955633-60fb008a-bce7-4b10-ab80-acf66bb4e633](https://github.com/user-attachments/assets/94507ef9-e697-49f6-900f-e8d0fcb33dd9)

**Procedure**

1.	Type the program in Quartus software.

2.	Compile and run the program.

3.	Generate the RTL schematic and save the logic diagram.

4.	Create nodes for inputs and outputs to generate the timing diagram.

5.	For different input combinations generate the timing diagram.


**Program:**

/* Program to implement the given logic function and to verify its operations in quartus using Verilog programming. 

Developed by: JAYANI K 
RegisterNumber: 24005008*/
~~~
module boolean_function_minimization(a, b, c, d, w, x, y, z, f1, f2);
 input a, b, c, d, w, x, y, z;
 output f1, f2;
 wire x1, x2, x3, x4, x5, x6, x7, x8, x9, x10;
 assign x1 = (~a) & (~b) & (~c) & (~d);
 assign x2 = (a) & (~c) & (~d);
 assign x3 = (~b) & (c) & (~d);
 assign x4 = (~a) & (b) & (c) & (d);
 assign x5 = (b) & (~c) & (d);
 assign f1 = x1 | x2 | x3 | x4 | x5;
 assign x6 = (x) & (~y) & (z);
 assign x7 = (~x) & (~y) & (z);
 assign x8 = (~w) & (x) & (y);
 assign x9 = (w) & (~x) & (y);
 assign x10 = (w) & (x) & (y);
 assign f2 = x6 | x7 | x8 | x9 | x10;
 endmodule
~~~
**RTL realization**
![391654580-0f4f6ac7-9e7e-4aa4-8521-373c487d70c6](https://github.com/user-attachments/assets/090e9d0a-2f43-4497-90b8-78621fb69f7c)

**Output:**

![312905303-8f9c13ca-3b42-462f-a28b-1096922a0f71](https://github.com/user-attachments/assets/ccece52c-e2f1-4705-943f-6fb14bc6fef8)

**RTL**
![390648562-e98204d2-529f-499e-8c41-9d74035f4c75](https://github.com/user-attachments/assets/69a779bd-3af5-416b-8d00-ff5569367235)

**Timing Diagram**
![391655215-45b6ef16-0880-4422-8156-81cc4a71d095](https://github.com/user-attachments/assets/105e2bb7-18d4-4c41-b03d-41634f132a74)

**Result:**

Thus the given logic functions are implemented using and their operations are verified using Verilog programming.

