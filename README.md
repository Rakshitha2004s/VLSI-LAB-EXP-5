# VLSI-LAB-EXP-5
SIMULATION AND IMPLEMENTATION OF FINITE STATE MACHINE

AIM: To simulate and synthesis finite state machine using vivado2023.3.

APPARATUS REQUIRED: vivado 2023.3

PROCEDURE:

STEP:1 Launch the Vivado 2023.2 software.

STEP:2 Click on “create project ” from the starting page of vivado.

STEP:3 Choose the design entry method:RTL(verilog/VHDL).

STEP:4 Crete design source and give name to it and click finish.

STEP:5 Write the verilog code and check the syntax.

STEP:6 Click “run simulation” in the navigator window and click “Run behavioral simulation”.

STEP:7 Verify the output in the simulation window.

Logic Diagram :

![image](https://github.com/navaneethans/VLSI-LAB-EXP-5/assets/6987778/34ec5d63-2b3b-4511-81ef-99f4572d5869)


VERILOG CODE:
```
module FSM_moore(clk, rst, x, z);
input clk, rst, x;
output z;
reg [2:1] present_state, NEXT_STATE;
parameter S0=2'b00, S1=2'b01, S2=2'b10, S3=2'b11;
// define the next state combinational circuit
always@(x,present_state)
case(present_state)
S0: if(x)
NEXT_STATE=S1;
else
NEXT_STATE=S0;
S1: if(x)
NEXT_STATE=S1;
else
NEXT_STATE=S2;
S2: if(x)
NEXT_STATE=S3;
else
NEXT_STATE=S0;
S3: if(x)
NEXT_STATE=S1;
else
NEXT_STATE=S2;
endcase
//define the sequential block
always@(negedge rst, posedge clk)
if(rst)
present_state<=S0;
else
present_state<=NEXT_STATE;
assign z=(present_state==S3); // define output
endmodule
```






OUTPUT:

![image](https://github.com/Rakshitha2004s/VLSI-LAB-EXP-5/assets/161333609/bf6ac581-36c3-4eb8-bf66-03ff96f5de84)



RESULT:

Thus the simulate and synthesis finite state machine using vivado2023.3 is verified


