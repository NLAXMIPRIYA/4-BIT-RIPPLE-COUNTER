# 4-BIT-RIPPLE-COUNTER

**AIM:**

To implement  4 Bit Ripple Counter using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 Bit Ripple Counter**

A binary ripple counter consists of a series connection of complementing flip-flops (T or JK type), with the output of each flip-flop connected to the Clock Pulse input of the next higher-order flip-flop. The flip-flop holding the least significant bit receives the incoming count pulses. The diagram of a 4-bit binary ripple counter is shown in Fig. below.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/cb4b74d4-31ab-4359-95d0-d22e67daba13)

In timing diagram Q0 is changing as soon as the negative edge of clock pulse is encountered, Q1 is changing when negative edge of Q0 is encountered(because Q0 is like clock pulse for second flip flop) and so on.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/a573a7d6-014e-4e54-93e6-e2ac9530960b)

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/85e1958a-2fc1-49bb-9a9f-d58ccbf3663c)

**Procedure**

/* write all the steps invloved */

**PROGRAM**
```
/* Program for 4 Bit Ripple Counter and verify its truth table in quartus using Verilog programming.

 Developed by:N LAXMI PRIYA
RegisterNumber:25010344
*/

**RTL LOGIC FOR 4 Bit Ripple Counter**
module ripcounter(clk,rst,t,A,B,C,D); 
input clk,rst,t; 
output A,B,C,D;
wire A,B,C,D;

TFlipFlop T0(D,clk,rst,t); 
TFlipFlop T1(C,D,rst,t); 
TFlipFlop T2(B,C,rst,t); 
TFlipFlop T3(A,B,rst,t); 

endmodule 



module TFlipFlop(q,clk,rst,t); 
input clk,rst,t; 
output reg q;

always @(posedge clk) 
begin 
    if(!rst)
        q <= 0;
    else
        q <= (t ? ~q : q);
end

endmodule

```



<img width="1051" height="512" alt="image" src="https://github.com/user-attachments/assets/013f29a3-97ce-4005-a816-1f398f9e66f4" />








**TIMING DIGRAMS FOR 4 Bit Ripple Counter**






<img width="1913" height="937" alt="image" src="https://github.com/user-attachments/assets/9de00f84-a6e2-478d-8d58-053835e5d347" />




**RESULTS**
