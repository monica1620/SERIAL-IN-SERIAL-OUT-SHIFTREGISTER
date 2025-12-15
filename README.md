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

1. Open Quartus Prime software and create a new new project.
2. Specify the project name and select the required working directory.
3. Choose the appropriate target device or FPGA family.
4. Create a new Verilog HDL file in the project.
5. Write the Verilog code to implement a 4-bit Serial-In Serial-Out (SISO) shift register.
6. Declare the clock input, serial input, and 4-bit output in the module.
7. Use a positive edge–triggered `always` block to control the shifting operation.
8. Assign the serial input to the first flip-flop and connect each flip-flop output to the next flip-flop input.
9. Save the Verilog file and compile the project to check for errors.
10. Perform RTL simulation to observe the shift operation.
11. Verify that the data shifts correctly on each clock pulse and appears serially at the output.


**PROGRAM**


**Developed by**: *Monica R*


**Register number**: *25010138*

```
module exp10(clk, sin, q);
input clk;
input sin;
output [3:0] q;
reg [3:0] q;
always @(posedge clk)
begin
q[0] <= sin;
q[1] <= q[0];
q[2] <= q[1];
q[3] <= q[2];
end
endmodule
```

**RTL LOGIC FOR SISO Shift Register**

<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/c30517de-463f-4b98-85f1-72e5a62149c3" />

**TIMING DIGRAMS FOR SISO Shift Register**
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/f38c8da5-5779-4e75-8bbb-dc5e038805e4" />


**RESULTS**
The 4-bit Serial-In Serial-Out (SISO) shift register was successfully implemented using Verilog HDL. The simulation results confirm that the input data is shifted one bit per clock pulse and appears at the output in a serial manner, validating correct operation.
