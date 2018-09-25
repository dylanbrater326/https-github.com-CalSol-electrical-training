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

Therefore, for resistors in series, the voltage across each is  V_i = I * R_i, and for the overall voltage: V = I (R<sub>1</sub> + R<sub>2</sub> + ... + R<sub>n</sub>). That shows that overall resistance for resistors in series is the sum of resistances.

Similarly, for resistors in parallel, the current across each is I_i = V / R_i, and the overall current is I = V( 1/R<sub>1</sub> + 1/R<sub>2</sub> + ... + 1/R<sub>n</sub>). R = 1/(1/R<sub>1</sub> + 1/R<sub>2</sub> + ... + 1/R<sub>n</sub>)

Using these rules solve the following problem:

#### Capacitors in Parallel and Series
To determine what the equivalent capacitance is for capacitors in series and in parallel, we are going to use the equation Q=CV.
For capacitors in parallel, the voltage across them is the same. The charge on each is Q_i = VC_i and the total charge is Q = V(C_1 + C_2 + ... + C_n). This means that the equivalent capacitance is the sum of the capacitors in parallel.
For capacitors in series, the current through them is the same. Since charge is the integral of current over time, the charge on the capacitors is the same. For each capacitor, V_i = Q/C_i, and the total voltage across each is V = Q(1/C_1 + 1/C_2 + ... + 1/C_n). Plugging back into the original equation, theq equivalent capacitance C=1/(1/C_1 + 1/C_2 + ... + 1/C_n)

Using these rules solve the following problem:

#### Switches
Switches are mechanical components that will connect two pins when it is in the "closed" state and will leave them disconnected in the "open" state.

#### LEDs
Light Emitting Diodes are diodes that light up when current is run through them. Diodes are devices that only allow current flow in one direction. In a schematic view, the arrow points in the direction of current flow. Because of this, LEDs are not reversible, they will only work in one orientation.
So what equation do we use to calculate the voltage drop across the LED and the current through it? We are going to use a simple model. Given a forward voltage from the datasheet, if the voltage across the diode (keep in mind the direction) is greater than the forward voltage, an infinite amount of current can flow. This means that in a circuit where the LED is on, the voltage across it is the forward voltage, regardless of the current. The current is controlled by the other elements in the circuit (usually a resistor). If the voltage across the diode is less than the forward voltage, then no current will flow and the LED will be off.
In each of the cases below, assume the forward voltage is 0.7V. In each case, is the LED on? How much current is going through the LED?


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
We're going to go through the process of designing the full circuit.
Start off by drawing the following symbol for the microcontroller on a piece of paper.

Photo Here

There's a pin at the top named VDD and a pin at the bottom named VSS. VDD is just another name for the power input and VSS is just another name for ground. Let's say we want to power the microcontroller from the battery. Draw a battery symbol, but don't connect the two just yet, because we also want to have a way of turning the circuit on and off. What should we add in between the battery and the microcontroller to allow for this functionality?
Additionally, we want a common ground for everything in the circuit, so connect the battery ground to the microcontroller ground. For the following parts keep in mind that the rest of the microcontroller pins can be software configured to be inputs or outputs, so it doesn't matter what pin you connect things to.

Now lets add 4 LEDs to the microcontroller. Lets say the microcontroller outputs are 3V and the forward voltage of the LEDs are 1V. What resistor should we add to each to limit the current to 2mA?

Lets add a button to the microcontroller, so that when its pressed, the microcontroller input reads 0V, and when its open, the microcontroller reads 3V. How should the switch be connected in order to drive 0V when the switch is closed? What do we need to being the voltage to 3V when the switch is open?

Finally, let's add the encoder. The pin in the middle is a ground pin, so let's connect that to ground. The top pin is pin A, and the bottom pin is pin B. Think about the model we use for the encoder, A and B are connected through a switch to ground. What do we need to make the voltage swing between 0V and 3V as the encoder turns?

## Conclusion
Next week, you'll be learning how to create this same circuit in the PCB design software we use, KiCAD.

