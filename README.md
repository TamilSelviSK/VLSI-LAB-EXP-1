# SIMULATE AND SYNTHESIS LOGIC GATES, ADDERS AND SUBTRACTOR USING VIVADO
## AIM: 
To simulate and synthesis Logic Gates, Adders and Subtractor using VIVADO

## APPARATUS REQUIRED:

VIVADO 2023.2

## PROCEDURE:

### STEP:1
Start the Vivado, Select and Name the New project.<br>

### STEP:2
Select the device family, device, package and speed. <br>

### STEP:3
Select new source in the New Project and select Verilog Module as the Source type.<br>

### STEP:4
Type the File Name and Click Next and then finish button. Type the code and save it.<br>

### STEP:5
Select the Behavioural Simulation in the Source Window and click the check syntax.<br>

### STEP:6
Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

## LOGIC-GATES:


![image](https://github.com/Sachita02/VLSI-LAB-EXP-1/assets/162723490/bdaada04-c2b8-4f66-b8e4-a2702e3721e3)




## PROGRAM:
```
module fs(a,b,c0,c1,c2,c3,c4,c5,c6);<br>
input a,b;<br>
output co,c1,c2,c3,c4,c5,c6;<br>
or g1 (co,a,b);<br>
and g2 (c1,a,b);<br>
xor g3 (c2,a,b);<br>
nand g4 (c3,a,b);<br>
nor g5 (c4,a,b);<br>
not g6(c5,a);<br>
xnor g7 (c6,a,b);<br>
endmodule
```

## OUTPUT: 

![image](https://github.com/Sachita02/VLSI-LAB-EXP-1/assets/162723490/021de699-0f77-4632-a0f6-7deffcd01153)


## HALF ADDER:

![image](https://github.com/Sachita02/VLSI-LAB-EXP-1/assets/162723490/de0676e2-b1d0-4971-8495-4f635430b9b8)


## PROGRAM:
```
module ha (a,b,s,c);<br>
input a,b;<br>
output s,c;<br>
xor g1(s,a,b); O and g2 (c,a,b);<br>
endmodule
```
## OUTPUT:
![image](https://github.com/Sachita02/VLSI-LAB-EXP-1/assets/162723490/3275efb9-cdf6-4c08-a664-d59012a6f962)


## HALFSUBTRACTOR:

![image](https://github.com/Sachita02/VLSI-LAB-EXP-1/assets/162723490/33d1f38d-513f-4011-a068-ae77c38919e6)


## PROGRAM:
```
module hs (a, b, diff, borr);<br>
input a,b;<br>
output diff, borr;<br>
xor gl (diff,a,borr); <br>
and g2 (borr, -a,b);<br>
endmodule
```
## OUTPUT:



![image](https://github.com/Sachita02/VLSI-LAB-EXP-1/assets/162723490/1607076b-4a0e-4ac0-af7a-71576b5708c2)







## FULLADDER:



![image](https://github.com/Sachita02/VLSI-LAB-EXP-1/assets/162723490/d6e5a1e0-6642-4689-a5c2-036147afb913)




## PROGRAM:
```
module fa (a,b,c,sum, carry);<br>
input a,b,c;<br>
output sum, carry;<br>
wire w1,w2,w3;<br>
xor gl(wl,a,b);<br>
xor g2 (w2,a,b);<br>
xor g3 (sum, w1,c);<br>
and (w3,c,w1);<br>
or g5 (carry, w3,w2);<br>
endmodule
```
## OUTPUT:

![image](https://github.com/Sachita02/VLSI-LAB-EXP-1/assets/162723490/ec22d9d0-87e1-40e7-b51d-e331834fc20f)


## FULLSUBTRACTOR:


![image](https://github.com/Sachita02/VLSI-LAB-EXP-1/assets/162723490/034e76f1-e216-4809-8e6c-ea1c4b8f38a8)




## PROGRAM:
```
module fs(a,b,c,diff,borrow);<br>
input a,b,c;<br>
output diff, borrow;<br>
wire w1,w2,w3;<br>
xor gl (wl,a,b);<br>
and g2 (w2,~a,b);<br>
xor g3 (diff,wl,c);<br>
and (w3,c,~wl); <br>
or g5 (borrow,w3,w2);<br>
endmodule
```
## OUTPUT:

![image](https://github.com/Sachita02/VLSI-LAB-EXP-1/assets/162723490/693c813d-d441-4548-9ca2-1c8f82631cbe)





## 8-BIT-RIPPLE-CARRY-ADDER:

![image](https://github.com/Sachita02/VLSI-LAB-EXP-1/assets/162723490/c247f68e-30a7-4fd8-b048-2ed221ba8389)


## PROGRAM:
```
module FA(a, b, c, sum, carry);<br>
input a, b, c;<br>
output sum, carry;<br>
assign sum=a ^ b ^ c;<br>
assign carry=a & b|b & c|a & c;<br>
endmodule<br>
<br>
module RCA(a, b, c, sum, carry);<br>
input [7:0] a, b;<br>
input c;<br>
output [7:0] sum;<br>
output carry;<br>
wire [6:0] w;<br>
FA f1(a[0], b[0], c, sum[0], w[0]);<br>
FA f2(a[1], b[1], w[0], sum[1], w[1]);<br>
FA f3(a[2], b[2], w[1], sum[2], w[2]);<br>
FA f4(a[3], b[3], w[2], sum[3], w[3]);<br>
FA f5(a[4], b[4], w[3], sum[4], w[4]);<br>
FA f6(a[5], b[5], w[4], sum[5], w[5]);<br>
FA f7(a[6], b[6], w[5], sum[6], w[6]);<br>
FA f8(a[7], b[7], w[6], sum[7], carry);<br>
endmodule
```

## OUTPUT:

![image](https://github.com/Sachita02/VLSI-LAB-EXP-1/assets/162723490/e3148bcd-38a4-4434-ae07-90eb14c749bb)


## RESULT:
	The simulate and synthesis Logic Gates, Adders and Subtractor using VIVADO is successfully verified.

