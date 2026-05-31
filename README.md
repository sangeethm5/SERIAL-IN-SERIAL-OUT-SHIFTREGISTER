# SERIAL-IN-SERIAL-OUT-SHIFTREGISTER

**AIM:**

To implement  SISO Shift Register using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**SISO shift Register**

A Serial-In Serial-Out shift register is a sequential logic circuit that allows data to be shifted in and out one bit at a time in a serial manner. It consists of a cascade of flip-flops connected in series, forming a chain. The input data is applied to the first flip-flop in the chain, and as the clock pulses, the data propagates through the flip-flops, ultimately appearing at the output.

The logic circuit provided below demonstrates a serial-in serial-out (SISO) shift register. It comprises four D flip-flops that are interconnected in a sequential manner. These flip-flops operate synchronously with one another, as they all receive the same clock signal.

![image](https://github.com/naavaneetha/SERIAL-IN-SERIAL-OUT-SHIFTREGISTER/assets/154305477/e81c4072-37f9-46c6-8145-566764b74c3a)

Figure 01 4 Bit SISO Register

The synchronous nature of the flip-flops ensures that the shifting of data occurs in a coordinated manner. When the clock signal rises, the input data is sampled and stored in the first flip-flop. On subsequent clock pulses, the stored data propagates through the flip-flops, moving from one flip-flop to the next.
Each D flip-flop in the circuit has a Data (D) input, a Clock (CLK) input, and an output (Q). The D input represents the data to be loaded into the flip-flop, while the CLK input is connected to the common clock signal. The output (Q) of each flip-flop is connected to the D input of the next flip-flop, forming a cascade.

**Procedure**

Step 1: Start the program and declare the inputs, outputs, clock, and reset signals for the SISO shift register.

Step 2: Write the Verilog module using flip-flops to shift the input data serially on every clock pulse.

Step 3: Apply different serial input bits and provide clock pulses to perform the shifting operation.

Step 4: Simulate the design in Quartus/ModelSim and verify the serial output using the functional table and waveform.


**PROGRAM**
```
module Exp10(clk,clear,si,so);
input clk,si,clear;
output so;
reg so;
reg [3:0] tmp;
always @(posedge clk )
begin
if (clear)
tmp <= 4'b0000;
else
tmp <= tmp << 1;
tmp[0] <= si;
so = tmp[3];
end
endmodule

```
```
Developed by: Sngeeth M
RegisterNumber:212225100043
```

**RTL LOGIC FOR SISO Shift Register**

<img width="1289" height="750" alt="Screenshot 2026-06-01 001943" src="https://github.com/user-attachments/assets/438c3c9b-bd2e-47af-b296-96ba6bcfb05e" />


**TIMING DIGRAMS FOR SISO Shift Register**

<img width="1920" height="361" alt="Screenshot 2026-06-01 002021" src="https://github.com/user-attachments/assets/9141d0eb-0229-4461-b4cc-534ecb79e096" />


**RESULTS**

This Verilog code implements a 4-bit left shift register with serial input si, serial output so, and synchronous clear control.
