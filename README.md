### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**

/* write all the steps invloved */

**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. 

Developed by:D.Varshini
RegisterNumber:212223230234
*/
```
module ex10(clk, sin, q);
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


**RTL LOGIC UP COUNTER**

![11o1](https://github.com/varshinidevaraju/SYNCHRONOUS-UP-COUNTER/assets/144870750/fef43564-80fc-4998-9146-1fa2d3433e0e)

**TIMING DIAGRAM FOR IP COUNTER**

![11o2](https://github.com/varshinidevaraju/SYNCHRONOUS-UP-COUNTER/assets/144870750/3dbac9e7-4108-4169-992d-4ac2388a96d6)


**TRUTH TABLE**

![11o3](https://github.com/varshinidevaraju/SYNCHRONOUS-UP-COUNTER/assets/144870750/9c8f53f2-7992-40c1-83ee-bf1c8cce7773)


**RESULTS**
SISO Shift Register using verilog and validating their functionality using their functional tables has successful execution of the program.
