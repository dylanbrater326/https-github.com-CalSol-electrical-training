# CalSol Electrical Workshop
## Lab 5: Introduction to Circuits
* Learn how components interact in small circuit
* See how different circuits are used to create a functional board

## Introduction
This lab is probably going to be a long one. It's going to be a crash course in EE, be sure to check out the lecture slides for quick explanations of different parts. Otherwise, buckle up and be ready to learn hardware!!

## THE LESSON
The next couple labs have the overall goal of you designing and building a circuit for a board that will have a battery, encoder, microcontroller, and some LEDs that you can blink. This week we're going over the full circuit on paper, walking you through the different parts and what each does.

### Components in Circuits

#### Resistors in Parallel and Series
Using Ohm's Law, we know that V = IR. Additionally, keep in mind Kirchhoff's Current Law (KCL) and Voltage Law (KVL). KVL states that the voltage across any loop is 0, and KCL states that sum of currents at any node is 0.
Using KCL and KVL, we can see that for series components, the current through them is the same, but the voltage across them is different. For parallel components, the voltage across them is the same, but the current through them is different.

Therefore, for resistors in series, the voltage across each is  V_i = I * R_i, and for the overall voltage: V = I (R_1 + R_2 + ... + R_n). That shows that overall resistance for resistors in series is the sum of resistances.

Similarly, for resistors in parallel, the current across each is I_i = V / R_i, and the overall current is I = V( 1/R_1 + 1/R_2 + ... + 1/R_n). R = 1/(1/R_1 + 1/R_2 + ... + 1/R_n)

Using these rules solve the following problem:

#### Capacitors in Parallel and Series

#### LEDs
Light Emitting Diodes are diodes that light up when current is run through them.


#### Sensors
In this lab we're only going to talk about one sensor, a rotary encoder.
The type of encoder we are going to use is a gray code encoder. It has two outputs, A and B. There is a third pin C, that should be connected to ground. Each of those two outputs can be thought of as a switch to ground. When you turn the encoder, it will connect one of the two to ground, followed by the other one, before returning both to an open circuit.
It is called grey code, because if you think of the combination as a binary number AB, where each equals 0 when its connected to ground and 1 when its open, only one bit changes at a time. You can tell which way the encoder is rotated by looking at which output pulses first.

Take a look at the signaling diagram at the bottom of page 2 [here](https://www.digikey.com/product-detail/en/tt-electronics-bi/EN11-HSM1AF15/987-1188-ND/2408766)

Complete the function below (Pseudocode is ok):
~~~~
bool A_last, B_last;
int get_rotation(bool A, bool B)
~~~~
A and B are the current inputs from the encoder, and get_rotation is called on every timestep
A_last and B_last are global variables that can be used to keep track of the last state of A and B (This isn't the best practice but it is ok for now, if you want more details on why global variables are not good practice ask a returning member)
The function should return -1 on a left turn, 0 on no change, and 1 on a right turn

### What They Do

#### Pullup and Pulldown Resistors
Imagine you have a switch connected to ground and an input pin on the microcontroller. The input pin can be approximated as an open circuit voltmeter. If the switch is closed, it conencts the microcontroller input to ground, so the input pin reads the voltage as 0V. If the switch is open, there is nothing driving the input pin on the microcontroller, so the voltage is undefined, and it could be anything. However, we want the microcontroller to read some voltage, ex. 1V, so it can detect a difference between when the switch is pressed and when its open. In order to fix this problem, we will connect a resistor from the input pin to 1V. When the switch is open, the input pin is now driven by the resistor, so the microcontroller will read 1V. This resistor is called a pullup resistor because it pulls the voltage up when nothing else is driving the wire. Similarly, you can have pulldown resistors that pull the voltage down to ground when the line is not driven.

#### Decoupling Capacitors
Microcontrollers and other chips often draw current in spikes. Because wires in real life have a small amount of resistance, this would cause voltage spikes (V = IR) from the power input to the mircocontroller. Capacitors limit the change in voltage because dV/dt = I/C. Having more capacitance reduces the voltage spikes, so we put capacitors right next to the power inputs for each chip.

#### Voltage Dividers
resistors current voltage led something current draw led rated to whatever so need some resistor to make blink, have some math about resistor values

#### RC Filters
Since capacitors oppose voltage changes we can make a frequency dependent circuit. Intuitavely, low frequency signals change slowly over time and high frequencies change quickly over time. That means that for higher frequencies, the voltage across the capacitor is smaller for a fixed current magnitude. With a resistor in series with the capacitor, the resistor limits current through the capacitor (don't think too much about the math). Therefore, as frequency increases, the voltage across the capacitor decreases. This is called a lowpass filter.

### The Full Circuit
start with the micro, say what you need to get a certain part to work and why, then make it a question about how to do that. goal is they draw things out on paper so i'll get pics of the components in kicad that we can add to the lab so they aren't completely clueless.

## Conclusion
Next week, you'll be learning how to create this same circuit in the PCB design software we use, KiCAD.

