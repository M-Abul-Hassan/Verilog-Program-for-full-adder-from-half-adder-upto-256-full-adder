# Verilog-Program-for-full-adder-from-half-adder-upto-256-full-adder

### short description
Verilog Program for XOR,Half adder,full adder,4 bit adder,16 bit,32 bit,64 bit ,128 bit and 256 bit full adder

# Verify Logic 
# XOR Gate
module xor_gate(output y,input a,b );  
wire [3:0]w;   
not(w[0],a);  
not(w[1],b);  
and(w[2],b,w[0]);  
and(w[3],a,w[1]);  
or(y,w[2],w[3]);  
endmodule  


# Half Adder
module xor_gate(output y,input a,b );  
wire [3:0]w;  
not(w[0],a);  
not(w[1],b);  
and(w[2],b,w[0]);    
and(w[3],a,w[1]);  
or(y,w[2],w[3]);  
endmodule    

# Procedure:  
####  Step#01   
Run simulation  
#### Step 2:    
Run synthesis    
#### Step 3:  
Run implementation    
#### Step4  
Run implementation design  
#### Step5:  
I/o planning select    
#### scalar ports are:  

IN          P4        LVCMOS33    
IN          P3        LVCMOS33     
IN          R3        LVCMOS33   
OUT         P2        LVCMOS33       
OUT         R2        LVCMOS33   

#### Step6:  
Generate bit stream    
open target (open hardware manager)  
Auto connect  
To generate bit stream file:   

add location:   

## FULL ADDER  
module full_adder(sum,carry,a,b,Cin);  
input a,b,Cin;   
output sum,carry;   
wire w1,w2,w3;  
half_adder Ha1 (w1,w2,a,b);   
half_adder Ha2 (sum,w3,w1,Cin);    
or (carry,w3,w2);   
endmodule   

module half_adder(S,C,A,B);   
input A,B;    
output S,C;   
xor_gate x1 (S,A,B);   
and (C,A,B);     
endmodule    


module xor_gate(D,A,B);     
input A,B;   
output D;  
wire [3:0] w;   
not (w[0],A);    
not (w[1],B);    
and (w[2],w[0],B);   
and (w[3],A,w[1]);   
or (D,w[2],w[3]);   
endmodule   
# 4BIT FULL ADDER   
Aim: Design and implement a 4 bit full adder.    

## DESIGN   

 ![image](https://github.com/M-Abul-Hassan/Verilog-Program-for-full-adder-from-half-adder-upto-256-full-adder/assets/118730309/a0345071-8c61-4a80-a4f5-29003b1e055f)



# Verilog Program- 4BIT FULL ADDER   

# 4BIT FULL ADDER  

//four bit adder  

module four_bit_adder(sum,cout,a,b,cin);   
input [3:0] a,b;     
input cin;   
output [3:0] sum;   
output cout;   
wire c_in2,c_in3,c_in4;
full_adder F1 (sum[0],c_in2,a[0],b[0],cin);   
full_adder F2 (sum[1],c_in3,a[1],b[1],c_in2);   
full_adder F3 (sum[2],c_in4,a[2],b[2],c_in3);   
full_adder F4 (sum[3],cout,a[3],b[3],c_in4);   
endmodule   
  
module full_adder(sum,carry,a,b,Cin);   
input a,b,Cin;   
output sum,carry;   
wire w1,w2,w3;    
half_adder Ha1 (w1,w2,a,b);   
half_adder Ha2 (sum,w3,w1,Cin);   
or (carry,w3,w2);    
endmodule   

module half_adder(S,C,A,B);   
input A,B;   
output S,C;   
xor_gate x1 (S,A,B);   
and (C,A,B);    
endmodule   


module xor_gate(D,A,B);    
input A,B;    
output D;     
wire [3:0] w;     
not (w[0],A);    
not (w[1],B);   
and (w[2],w[0],B);  
and (w[3],A,w[1]);   
or (D,w[2],w[3]);   
endmodule   

# Procedure:   
Step#01   
Run simulation   
Step 2:      
Run synthesis   
Step 3:   
Run implementation   
Step4   
Run implementation design   
Step5:   
I/o planning select   
scalar ports are:   

IN          P4        LVCMOS33    
IN          P3        LVCMOS33   
IN          R3        LVCMOS33   
OUT         P2        LVCMOS33   
OUT         R2        LVCMOS33   

Step6:   
Generate bit stream    
open target (open hardware manager)   
Auto connect   
To generate bit stream file:   

add location:    

## Timing diagram:   
## Simulation:   

![image](https://github.com/M-Abul-Hassan/Verilog-Program-for-full-adder-from-half-adder-upto-256-full-adder/assets/118730309/dcba448c-df64-4e0f-a4f5-833c480d9410)


![image](https://github.com/M-Abul-Hassan/Verilog-Program-for-full-adder-from-half-adder-upto-256-full-adder/assets/118730309/0927ec24-a741-44df-a930-4186fa7bed82)

 
![image](https://github.com/M-Abul-Hassan/Verilog-Program-for-full-adder-from-half-adder-upto-256-full-adder/assets/118730309/73661611-07d5-4753-90a9-43ab7d01bca7)



 
 ![image](https://github.com/M-Abul-Hassan/Verilog-Program-for-full-adder-from-half-adder-upto-256-full-adder/assets/118730309/014023fb-c112-4d8f-ac53-2a68c671f5a5)



 

# 16BIT FULL ADDER    
//16 bit adder    

module sixteen_bit_adder(sum,cout,A,B,Cin);   
input [15:0] A,B;   
input Cin;  
output [15:0] sum;   
output cout;   
wire c_in4,c_in8,c_in12;   
four_bit_adder F1(sum[3:0],c_in4,A[3:0],B[3:0],Cin);   
four_bit_adder F2(sum[7:4],c_in8,A[7:4],B[7:4],c_in4);   
four_bit_adder F3(sum[11:8],c_in12,A[11:8],B[11:8],c_in8);   
four_bit_adder F4(sum[15:12],cout,A[15:12],B[15:12],c_in12);    
endmodule   
module four_bit_adder(sum,cout,a,b,cin);   
input [3:0] a,b;   
input cin;   
output [3:0] sum;   
output cout;   
wire c_in2,c_in3,c_in4;   
full_adder F1 (sum[0],c_in2,a[0],b[0],cin);   
full_adder F2 (sum[1],c_in3,a[1],b[1],c_in2);   
full_adder F3 (sum[2],c_in4,a[2],b[2],c_in3);   
full_adder F4 (sum[3],cout,a[3],b[3],c_in4);   
endmodule   
module full_adder(sum,carry,a,b,Cin);   
input a,b,Cin;    
output sum,carry;   
wire w1,w2,w3;   
half_adder Ha1 (w1,w2,a,b);   
half_adder Ha2 (sum,w3,w1,Cin);   
or (carry,w3,w2);   
endmodule   

module half_adder(S,C,A,B);   
input A,B;   
output S,C;   
xor_gate x1 (S,A,B);   
and (C,A,B);   
endmodule   
   
  
module xor_gate(D,A,B);   
input A,B;   
output D;   
wire [3:0] w;  
not (w[0],A);  
not (w[1],B);  
and (w[2],w[0],B);  
and (w[3],A,w[1]);   
or (D,w[2],w[3]);   
endmodule   
  
## 64BIT FULL ADDER   
	//64 bit adder  

module sixty_four_bit_adder(SUM,COUT,A,B,CIN);   
input [63:0] A,B;   
input CIN;  
output [63:0] SUM;  
output COUT;   
wire c_in16,c_in32,c_in48;   
sixteen_bit_adder S1 (SUM[15:0],c_in16,A[15:0],B[15:0],CIN);   
sixteen_bit_adder S2 (SUM[31:16],c_in32,A[31:16],B[31:16],c_in16);  
sixteen_bit_adder S3 (SUM[47:32],c_in48,A[47:32],B[47:32],c_in32);   
sixteen_bit_adder S4 (SUM[63:48],COUT,A[63:48],B[63:48],c_in48);   
endmodule   
module sixteen_bit_adder(sum,cout,A,B,Cin);   
input [15:0] A,B;   
input Cin;   
output [15:0] sum;   
output cout;   
wire c_in4,c_in8,c_in12;   
four_bit_adder F1(sum[3:0],c_in4,A[3:0],B[3:0],Cin);  
four_bit_adder F2(sum[7:4],c_in8,A[7:4],B[7:4],c_in4);   
four_bit_adder F3(sum[11:8],c_in12,A[11:8],B[11:8],c_in8);   
four_bit_adder F4(sum[15:12],cout,A[15:12],B[15:12],c_in12);   
endmodule   
module four_bit_adder(sum,cout,a,b,cin);   
input [3:0] a,b;  
input cin;   
output [3:0] sum;   
output cout;   
wire c_in2,c_in3,c_in4;   
full_adder F1 (sum[0],c_in2,a[0],b[0],cin);   
full_adder F2 (sum[1],c_in3,a[1],b[1],c_in2);  
full_adder F3 (sum[2],c_in4,a[2],b[2],c_in3);   
full_adder F4 (sum[3],cout,a[3],b[3],c_in4);   
endmodule   
module full_adder(sum,carry,a,b,Cin);   
input a,b,Cin;   
output sum,carry;   
wire w1,w2,w3;   
half_adder Ha1 (w1,w2,a,b);  
half_adder Ha2 (sum,w3,w1,Cin);   
or (carry,w3,w2);   
endmodule   
     
module half_adder(S,C,A,B);   
input A,B;  
output S,C;   
xor_gate x1 (S,A,B);  
and (C,A,B);   
endmodule  
   
  
module xor_gate(D,A,B);  
input A,B;   
output D;   
wire [3:0] w;   
not (w[0],A);   
not (w[1],B);   
and (w[2],w[0],B);   
and (w[3],A,w[1]);   
or (D,w[2],w[3]);   
endmodule  

## 256 BIT FULL ADDER   
  
//256 bit adder   
  
module two_fifty_six_bit_adder(SUM,COUT,A,B,CIN);   
input [255:0] A,B;   
input CIN;   
output [256:0] SUM;  
output COUT;   
wire c_in64,c_in128,c_in192;   
sixty_four_bit_adder S1 (SUM[63:0],c_in64,A[63:0],B[63:0],CIN);   
sixty_four_bit_adder S2 (SUM[127:64],c_in128,A[127:64],B[127:64],c_in64);   
sixty_four_bit_adder S3 (SUM[191:128],c_in192,A[191:128],B[191:128],c_in128);   
sixty_four_bit_adder S4 (SUM[255:192],COUT,A[255:192],B[255:192],c_in192);   
endmodule   
   
module sixty_four_bit_adder(SUM,COUT,A,B,CIN);   
input [63:0] A,B;   
input CIN;   
output [63:0] SUM;   
output COUT;   
wire c_in16,c_in32,c_in48;   
sixteen_bit_adder S1 (SUM[15:0],c_in16,A[15:0],B[15:0],CIN);      
sixteen_bit_adder S2 (SUM[31:16],c_in32,A[31:16],B[31:16],c_in16);   
sixteen_bit_adder S3 (SUM[47:32],c_in48,A[47:32],B[47:32],c_in32);   
sixteen_bit_adder S4 (SUM[63:48],COUT,A[63:48],B[63:48],c_in48);   
endmodule   
module sixteen_bit_adder(sum,cout,A,B,Cin);   
input [15:0] A,B;    
input Cin;   
output [15:0] sum;    
output cout;   
wire c_in4,c_in8,c_in12;   
four_bit_adder F1(sum[3:0],c_in4,A[3:0],B[3:0],Cin);   
four_bit_adder F2(sum[7:4],c_in8,A[7:4],B[7:4],c_in4);     
four_bit_adder F3(sum[11:8],c_in12,A[11:8],B[11:8],c_in8);    
four_bit_adder F4(sum[15:12],cout,A[15:12],B[15:12],c_in12);   
endmodule   
module four_bit_adder(sum,cout,a,b,cin);   
input [3:0] a,b;   
input cin;   
output [3:0] sum;   
output cout;   
wire c_in2,c_in3,c_in4;   
full_adder F1 (sum[0],c_in2,a[0],b[0],cin);   
full_adder F2 (sum[1],c_in3,a[1],b[1],c_in2);   
full_adder F3 (sum[2],c_in4,a[2],b[2],c_in3);   
full_adder F4 (sum[3],cout,a[3],b[3],c_in4);   
endmodule   
   
module full_adder(sum,carry,a,b,Cin);   
input a,b,Cin;   
output sum,carry;   
wire w1,w2,w3;   
half_adder Ha1 (w1,w2,a,b);     
half_adder Ha2 (sum,w3,w1,Cin);   
or (carry,w3,w2);   
endmodule   
module half_adder(S,C,A,B);   
input A,B;   
output S,C;         
xor_gate x1 (S,A,B);    
and (C,A,B);    
endmodule   
  
   
module xor_gate(D,A,B);    
input A,B;   
output D;   
wire [3:0] w;   
not (w[0],A);    
not (w[1],B);     
and (w[2],w[0],B);    
and (w[3],A,w[1]);   
or (D,w[2],w[3]);   
endmodule   
  
   

## Hardware Implementation On NEXYS 4(Artix-7 Power)

![WhatsApp Image 2023-04-28 at 10 20 23 AM](https://user-images.githubusercontent.com/118730309/235071152-9788071e-e3c3-446f-99a1-7b697cd8f40f.jpeg)


![WhatsApp Image 2023-04-28 at 10 21 01 AM](https://user-images.githubusercontent.com/118730309/235071377-4e738fb4-71b4-4cf2-89fd-8a3447b4f6ba.jpeg)




--------THE END--------   


