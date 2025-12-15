
# AIM:

To implement SR flipflop using verilog and validating their functionality using their functional tables

# SOFTWARE REQUIRED:

Quartus prime

# THEORY

SR Flip-Flop SR flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.

<img width="769" height="452" alt="Screenshot 2025-12-15 135627" src="https://github.com/user-attachments/assets/f291dd1c-d47f-4923-b0ad-52c6a40106d9" />


This circuit has two inputs S & R and two outputs Qtt & Qtt’. The operation of SR flipflop is similar to SR Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable. The following table shows the state table of SR flip-flop.

<img width="817" height="451" alt="Screenshot 2025-12-15 135716" src="https://github.com/user-attachments/assets/a0f57751-bc00-4e59-8ffc-4304bad2ad82" />


Here, Qtt & Qt+1t+1 are present state & next state respectively. So, SR flip-flop can be used for one of these three functions such as Hold, Reset & Set based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of SR flip-flop. Present Inputs Present State Next State

<img width="660" height="555" alt="Screenshot 2025-12-15 135725" src="https://github.com/user-attachments/assets/8f71a98a-9ac3-4644-84db-e1bc6b95dbc5" />


By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. The three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

<img width="383" height="264" alt="Screenshot 2025-12-15 135735" src="https://github.com/user-attachments/assets/0850551f-7dd0-4164-8d77-f845278634ed" />


The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=S+R′Q(t)Q(t+1)=S+R′Q(t)

# Procedure

1 Open Quartus software and create a new project.

2 Create a new VHDL file and write the code for the SR Flip Flop.

3 Compile the design by clicking on "Processing" -> "Start Compilation".

4 Create a testbench file to simulate the design.

5 Write the testbench code and add stimulus to test the SR Flip Flop.

6 Run the simulation by clicking on "Processing" -> "Start Simulation".

7 Observe the waveforms and verify the SR Flip Flop behavior.

8 Analyze the results and make any necessary changes to the design.


# PROGRAM

# Developed by: HARINI G
# RegisterNumber: 25015377
SR flip-flop (with async reset)

module SR_flipflop (

    input  wire clk, rst, S, R,
    
    output reg  Q
    
);

    always @(posedge clk) begin
    
        if (rst)
        
            Q <= 1'b0;        
            
        else begin
            case ({S,R})
                2'b00: Q <= Q;   
                
                2'b01: Q <= 1'b0;  
                
                2'b10: Q <= 1'b1;  
                
                2'b11: Q <= 1'bx; 
                
            endcase
            
        end
        
    end
    
endmodule

# RTL LOGIC FOR FLIPFLOPS

<img width="1314" height="642" alt="Screenshot 2025-12-05 223349" src="https://github.com/user-attachments/assets/a9cc0874-8016-4a94-848f-560c0e36bdea" />

# TIMING DIGRAMS FOR FLIP FLOPS

<img width="1879" height="985" alt="Screenshot 2025-12-15 110948" src="https://github.com/user-attachments/assets/a9d1fda7-3284-4a88-9f8b-23ca99b941cc" />

# RESULTS

Thus the JK flipflop is implemented and verified.

