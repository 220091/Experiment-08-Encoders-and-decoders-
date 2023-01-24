 Experiment-08- Encoders-and-decoders 
 
 AIM: To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
 
 HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
 
 SOFTWARE REQUIRED:   Quartus prime
 
 THEORY 
 
 
 

 Encoders
 
Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

1. Encoders –
An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.

As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.

![image](https://user-images.githubusercontent.com/36288975/171543588-bc0746df-a173-4b35-989e-5fb7d385fe8a.png)
 Figure -01 3 to 8 Encoder 


Implementation –

X = D4 + D5 + D6 + D7
Y = D2 +D3 + D6 + D7
Z = D1 + D3 + D5 + D7 
Hence, the encoder can be realised with OR gates as follows:


![image](https://user-images.githubusercontent.com/36288975/171543740-68403b82-aa93-4c98-9343-f32b14885a2e.png)
 Figure -02 3 to 8 Encoder implenentation 

  Decoders 
A decoder does the opposite job of an encoder. It is a combinational circuit that converts n lines of input into 2n lines of output.

Let’s take an example of 3-to-8 line decoder.
Implementation –
D0 is high when X = 0, Y = 0 and Z = 0. Hence,

D0 = X’ Y’ Z’ 
Similarly,

D1 = X’ Y’ Z
D2 = X’ Y Z’
D3 = X’ Y Z
D4 = X Y’ Z’
D5 = X Y’ Z
D6 = X Y Z’
D7 = X Y Z 


![image](https://user-images.githubusercontent.com/36288975/171543978-ee2d0671-2846-40a1-8705-507fd6287a49.png)
 Figure -03 8 to 3 Decoder 



![image](https://user-images.githubusercontent.com/36288975/171543866-5a6eace6-8683-49d7-9c4f-a7cb30ec3035.png)
Figure -04 8 to 3 Decoder implementation 

Procedure


Step 1:
Open Quartus II and select new project and choose the file location.

Step 2:
Module Declaration. Module should have the file name.

Step 3:
Input-Output Delecaration.

Step 4:
Use assign to define the functionality of logic circuits.

Step 5:
At the end give endmodule.

Step 6:
Run the program and choose RTL viewer to get RTL realization.




 PROGRAM 
 
 
 FOR ENCODER
 
 
 module encode(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
 
output a,b,c;

input d0,d1,d2,d3,d4,d5,d6,d7;

or(a,d4,d5,d6,d7);

or(b,d2,d3,d6,d7);

or(c,d1,d3,d5,d7);

endmodule


FOR DECODER

module decode(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);

output d0,d1,d2,d3,d4,d5,d6,d7;

input a,b,c;

assign d0 = (~a&~b&~c);

assign d1 = (~a&~b&c);

assign d2 = (~a&b&~c);

assign d3 = (~a&b&c);

assign d4 = (a&~b&~c);

assign d5 = (a&~b&c);

assign d6 = (a&b&~c);

assign d7 = (a&b&c);

endmodule



Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.

Developed by: Jenifer.A

RegisterNumber:  22009141




 RTL LOGIC  

FOR ENCODER


![RTL SSS](https://user-images.githubusercontent.com/121572543/214370912-d6f7436f-9d9e-4216-89f0-87609c8bdf0f.png)


FOR DECODER

 ![RTL 2 SSSS](https://user-images.githubusercontent.com/121572543/214372010-59633857-ff6a-4b41-b59d-a70af919df5b.png)







TIMING DIAGRAMS

FOR ENCODER


![TT SSS](https://user-images.githubusercontent.com/121572543/214372416-3be035c8-1b9d-465f-8b0b-8b6d862297f8.png)



FOR DECODER


![TT 2 SSS](https://user-images.githubusercontent.com/121572543/214372940-4bf33401-b41f-4d73-86d5-367da5c5586c.png)





 TRUTH TABLE 
 
 FOR ENCODER
 
  
 ![TD SSS](https://user-images.githubusercontent.com/121572543/214373920-6540e081-3371-4b3a-9696-05d3c5958e76.png)

 
 
 
 FOR DECODER
 
 
 ![TD 2SSS](https://user-images.githubusercontent.com/121572543/214374521-f8bf82df-b5fb-4ffb-911e-329edc4ee937.png)



 RESULTS 


 to 3 Encoder and 3to8 Decoder has been implemented by using verilog and its outputs are validated.

