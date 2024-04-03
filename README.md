# VLSI LAB EXPERIMENT 01
## SIMULATION AND IMPLEMENTATION OF LOGIC GATES ANd 4 BIT ADDER & SUBTRACTOR 
### AIM:
To simulate and synthesis Logic Gates, Adders and Subtractor using VIVADO
### APPARATUS REQUIRED:
VIVADO 2023.2
### PROCEDURE:
 STEP:1 Start the Vivado, Select and Name the New project. 

 
 STEP:2 Select the device family, device, package and speed. 

 
 STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

 
 STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it.

 
 STEP:5 Select the Behavioural Simulation in the Source Window and click the check syntax.

 
 STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

 
## LOGIC-GATES:
![image](https://github.com/Sricharumathy/HDL-Programming/assets/159044760/82dcd0f0-6349-431d-9e34-0358e3ae1773)
## Program:
```
module LG(a, b, c0, c1, c2, c3, c4, c5, c6);
input a, b;
output c0, c1, c2, c3, c4, c5, c6;
and(c0, a, b);
or(c1, a, b);
xor(c2, a, b);
nand(c3, a, b);  
nor(c4, a, b);
xnor(c5, a, b);
not(c6, a);
endmodule
```
## Output
![image](https://github.com/Sricharumathy/HDL-Programming/assets/159044760/ebcf71dc-a933-4321-9acd-0755217bb27d)

## Half Adder:
![image](https://github.com/Sricharumathy/HDL-Programming/assets/159044760/71407301-2078-4778-b822-4154f739fe4d)
## Program
```
module HA (a, b, sum, carry);
input a, b;
output sum, carry;
xor g1(sum, a, b); 
and g2 (carry, a, b);
endmodule
```
## Output
![image](https://github.com/Sricharumathy/HDL-Programming/assets/159044760/d398bc14-f3d7-457c-96c3-0f62205fea17)

## Half Subtractor:
![image](https://github.com/Sricharumathy/HDL-Programming/assets/159044760/bdc11a7c-42cf-4cb8-8d7a-e0798e892955)
## Program
```
module HS (a, b, diff, borrow);
input a, b;
output diff, borrow;
xor gl (diff, a, b); 
and g2 (borrow,  ~a, b);
endmodule
```
## Output 
![image](https://github.com/Sricharumathy/HDL-Programming/assets/159044760/d20b079f-2393-4d1f-ab82-e820b0b35f57)


## Full Adder:
![image](https://github.com/Sricharumathy/HDL-Programming/assets/159044760/afb2a790-069c-437a-aada-77b470ff5956)
## Program
```
module FA(a, b, c, sum, carry);
input a, b, c;
output sum, carry;
wire w1, w2, w3;
xor g1(w1, a, b);
and g2(w2, a, b);
xor g3(sum, w1 ,c);
and g4(w3, w1, c);
or  g5(carry, w3, w2);
endmodule
```
## Output
![image](https://github.com/Sricharumathy/HDL-Programming/assets/159044760/681e6140-291b-4c05-8fe0-e390cf90b319)


## Full Subtractor:
![image](https://github.com/Sricharumathy/HDL-Programming/assets/159044760/8741381a-a75e-43fe-99a8-2c93119e6e4d)
## Program
```
module FS(a, b, c, diff, borrow);
input a, b, c;
output diff, borrow;
wire x, y, z;
xor g1(x, a, b);
and g2(y, ~a , b);
xor g3(diff, x, c);
and g4(z, c, ~x);
or  g5(borrow, y, z);
endmodule
```
## Output
![image](https://github.com/Sricharumathy/HDL-Programming/assets/159044760/66b1cb39-57c7-4006-a82b-f2a6458ba42f)

## Ripple Carry Adder:
![image](https://github.com/Sricharumathy/HDL-Programming/assets/159044760/bc98a322-11d7-47e4-a8ca-1d3ddfd4adca)
## Program
```
module FA(a, b, c, sum, carry);
input a, b, c;
output sum, carry;
assign sum=a ^ b ^ c;
assign carry=a & b|b & c|a & c;
endmodule

module RCA(a, b, c, sum, carry);
input [7:0] a, b;
input c;
output [7:0] sum;
output carry;
wire [6:0] w;
FA f1(a[0], b[0], c, sum[0], w[0]);
FA f2(a[1], b[1], w[0], sum[1], w[1]);
FA f3(a[2], b[2], w[1], sum[2], w[2]);
FA f4(a[3], b[3], w[2], sum[3], w[3]);
FA f5(a[4], b[4], w[3], sum[4], w[4]);
FA f6(a[5], b[5], w[4], sum[5], w[5]);
FA f7(a[6], b[6], w[5], sum[6], w[6]);
FA f8(a[7], b[7], w[6], sum[7], carry);
endmodule
```
## Output
![image](https://github.com/Sricharumathy/HDL-Programming/assets/159044760/6c5666c4-fd23-4460-b1eb-9e8bdf7ff854)
## Result:
Thus, the logic gates and 4 Bit of Adder and Subtractor are implemented and simulated successfully.
                      






















