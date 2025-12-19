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
Open Quartus Prime and create a new project.

Select the target FPGA device.

Create a new Verilog/VHDL file.

Design four JK flip-flops and connect all clock inputs to a common clock.

Connect J = K = 1 (Vcc) for the first (LSB) flip-flop so that it toggles at every clock pulse.

Connect J₁ = K₁ = Q₀ for the second flip-flop so it toggles when the first flip-flop output is HIGH.

Use an AND gate to connect J₂ = K₂ = Q₀ · Q₁ for the third flip-flop.

Use a 3-input AND gate to connect J₃ = K₃ = Q₀ · Q₁ · Q₂ for the fourth flip-flop.

Compile the design and check for errors.

Open Simulation Waveform Editor.

Apply clock pulses and observe the output sequence:

0000 → 0001 → 0010 → 0011 → ... → 1111


Verify that all flip-flops toggle synchronously at the same clock edge.

**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. 

Developed by:G.Muthu Manikkam RegisterNumber:25016274
*/
<img width="891" height="463" alt="exp11 (Program)" src="https://github.com/user-attachments/assets/99f29b8b-630f-4fde-8ede-b231de8525e3" />


**RTL LOGIC UP COUNTER**
<img width="1465" height="747" alt="exp11(RTL Diagram)" src="https://github.com/user-attachments/assets/7a4b1873-97f3-4fc2-8a99-07fecb8eb02d" />

**TIMING DIAGRAM FOR IP COUNTER**
<img width="1918" height="972" alt="exp11(Waveform)" src="https://github.com/user-attachments/assets/d8f0ec43-66a8-4087-bc33-bf1089318b65" />

**TRUTH TABLE**

**RESULTS**
A 4-bit synchronous up counter is successfully designed and verified using Quartus, producing correct binary up-counting
