# Experiment-no2
### Design the mpliefier confuguration using tsmc in LTSPICE
### AIM :
To design a Common Source (CS) amplifier-configurations using NMOSFET in tsmc 180nm tech.lib in LTspice and to perform DC, Transient and AC analysis as per the given specifications.

1.Common source Amplifier with source degeneration.
2.Cascode amplifier.
3.Current mirror loaded common source amplifier.

### Introduction :
Analog amplifier circuits are fundamental building blocks in electronic systems. They are used to increase the amplitude of weak electrical signals so that they can be processed by other stages in an electronic system. Amplifiers are widely used in communication systems, signal processing, and integrated circuit (IC) design.

In this project, different amplifier configurations are designed and simulated using LTspice, a SPICE-based circuit simulation software developed by Analog Devices. LTspice allows engineers and students to model MOSFET devices and evaluate important parameters such as voltage gain, frequency response, input impedance, output impedance, and power consumption.These circuits are designed using TSMC MOSFET models and analyzed through simulation. The results help in understanding the behavior of CMOS amplifiers and provide practical experience in analog IC design using simulation tools.

### MOSFET Amplifier Fundamentals:
MOSFET amplifiers are used to increase the amplitude of small input signals.
For proper amplification, the MOSFET must operate in the saturation region, where it behaves like a controlled current source.

### Important Parameters
1)Drain Current (ID)
ID = (1/2) μCox (W/L) (VGS − VTH)²

2)Overdrive Voltage (Vov)
Vov = VGS − VTH

3)Transconductance (gm)
gm = 2ID / Vov

4)Output Resistance (ro)
ro = 1 / (λID)

5)Voltage Gain (Av)
Av = −gm × Rout

### Amplifier Configurations Overview:
### 1. Source Degenerated Common Source
Uses a source resistor to introduce negative feedback.
Advantage: Improves bias stability and linearity.
Limitation: Reduces voltage gain.
### 2. Cascode Amplifier
Combination of Common Source + Common Gate stages.
Advantage: Provides high output resistance and higher gain.
Limitation: More complex circuit design.

### 3. Active Load Common Source
Uses a current mirror or active transistor load instead of a resistor.
Advantage: Achieves higher gain.
Limitation: Sensitive to biasing conditions.
### CONFIGURATION - 1

### CIRCUIT DIAGRAM :
![Image description]

CMOS Common Source Amplifier with Active Load
### Circuit description :
This circuit represents a CMOS common-source amplifier that uses an NMOS transistor as the amplifying device and a PMOS transistor as an active load. The design is commonly used in analog integrated circuits for small-signal voltage amplification.
The circuit consists of several important components that work together to perform amplification.

The circuit consists of several important components that work together to perform amplification.

**1) M1 (PMOS transistor)** is used as an active load in the circuit. It is connected to the supply voltage and helps control the current flowing through the amplifier. By acting as an active load, it improves the voltage gain of the circuit.

**2) M2 (NMOS transistor)** acts as the main amplifying device. The input signal is applied to its gate terminal, and it controls the current flowing through the circuit based on the input voltage. This change in current produces the amplified output signal.

**3) V1 (2 V)** is the power supply of the circuit, commonly referred to as (V_{DD}). It provides the necessary voltage required for the operation of the transistors.

**4) V3 (1.36 V)** is a bias voltage applied to the gate of the PMOS transistor. This biasing ensures that the PMOS transistor operates in the correct region so that it can function properly as an active load.

**5) V2** is the input signal source. The signal applied here is the one that needs to be amplified by the circuit.

A **6) 1 kΩ resistor** is connected to the source terminal of the NMOS transistor. This resistor acts as a source degeneration resistor and helps improve the stability and linearity of the amplifier by providing negative feedback.

The **output voltage (Vout)** is taken from the node where the drain terminals of the PMOS transistor (M1) and NMOS transistor (M2) are connected. This node produces the amplified version of the input signal.

### Input Signal
The input voltage is defined as:

SINE(0.8 10m 1000)

Where:

0.8 V = DC offset
10 mV = Amplitude of the input signal
1000 Hz = Frequency of the signal
### Circuit Operation
The input signal is applied to the gate of the NMOS transistor (M2).
Variations in the input voltage change the gate-to-source voltage (VGS) of M2.
This variation controls the drain current flowing through M2.
The PMOS transistor (M1) acts as an active load, providing a nearly constant current and improving voltage gain.
The output voltage (Vout) is measured at the node between M1 and M2.
Output Behavior
When Vin increases, the NMOS conducts more current, causing Vout to decrease.
When Vin decreases, the NMOS conducts less current, causing Vout to increase.
This results in an inverted amplified output signal.

### Source Degeneration
The 1kΩ resistor connected to the source of M2 provides:

Improved linearity
Bias stability
Reduced distortion
### THEORY :
Circuit Components
The circuit consists of the following main components:

NMOS transistor acting as the amplifying device
PMOS transistor acting as the active load
Source degeneration resistor (Rs)
Bias voltage (VB) for proper transistor operation
Output node taken from the drain terminal
PMOS Active Load
Instead of using a passive resistor as the load, a PMOS transistor is used as an active load.
The PMOS transistor provides a higher output resistance compared to a conventional resistor, which helps in increasing the voltage gain of the amplifier.

Using a PMOS transistor as a load also makes the circuit more suitable for integrated circuit (IC) implementation, since large resistors consume significant chip area.

### Source Degeneration
A source resistor (Rs) is connected to the source of the NMOS transistor.
This configuration is known as source degeneration.

The resistor introduces negative feedback into the circuit. When the current through the NMOS increases, the voltage drop across Rs also increases, which reduces the effective gate-to-source voltage (Vgs). This helps control the current flowing through the transistor.
Effects of Source Degeneration
The source degeneration resistor provides several advantages:

Improves the linearity of the amplifier
Helps stabilize the operating (bias) point
Reduces signal distortion
Slightly reduces the overall voltage gain
### Design Calculations :
### 1. Drain Current (ID)
For the NMOS transistor operating in saturation region:

ID = (1/2) * μn * Cox * (W/L)n * (VGS − VTN)^2

Where:

μn = Electron mobility
Cox = Oxide capacitance per unit area
(W/L)n = Aspect ratio of NMOS transistor
VGS = Gate to source voltage
VTN = Threshold voltage of NMOS Given Specifications:
VDD = 2 V
ID = 200 µA
VOV = 0.25 V
CL = 1 pF
Ln = Lp = 180 nm
P<= 1.5mW
εr = 3.9
ε0 = 8.854 × 10⁻¹² F/m
tox = 4.1 × 10⁻⁹ m
μn = 273.809 cm²/Vs
μp = 115.689 cm²/Vs Power constraint:Assuming ID =200µA which satisfy P<=1.5mW (P=V*I ; 2×200×10^−6 ; 400µW<=1.5mW)

### 2. Transconductance (gm)
The transconductance of the NMOS transistor is given by:

gm = 2ID / (VGS − VTN)

### 4. Voltage Gain (Av)
For a common source amplifier with source degeneration:

Av = - gm (ron || rop) / (1 + gmRs)

Where:

gm = Transconductance of NMOS
Rs = Source degeneration resistor
ron = Output resistance of NMOS
rop = Output resistance of PMOS
The negative sign indicates phase inversion

 


