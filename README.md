# Experiment-no2
### CS amplifier with different configurations:
### CS amplifier with resistor load:
### AIM :
Design CS Amplifier using NMOSFET in tsmc 180nm using VDD=2V, P<=1.2mW, C=1pF, Ln=480nm

### Introduction :
A Common Source (CS) amplifier with resistor load is one of the most basic and widely used amplifier circuits in analog electronics, especially when working with MOSFETs. the MOSFET is the main device that controls the signal, and the resistor connected at the drain acts as a load that helps convert current changes into voltage changes.In this setup, the input signal is applied to the gate of the MOSFET, the source is usually connected to ground (hence the name “common source”), and a resistor is connected at the drain to the supply voltage. The output is taken from the drain terminal.

Now, when a small input voltage is given at the gate, it changes the current flowing through the MOSFET. This changing current passes through the drain resistor, which creates a varying voltage across it. As a result, we get an amplified output voltage at the drain.One important thing to notice is that the output signal is inverted compared to the input. That means if the input goes up, the output goes down, and vice versa. This happens because of how the voltage drop across the resistor changes with current.

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

### CIRCUIT DIAGRAM :
![Image description](https://github.com/2024ecdeekshithagjc-bit/Experiment-no2/blob/main/circuit1.png?raw=true)
CMOS Common Source Amplifier with Active Load
### Circuit description :
This circuit is a Common Source (CS) amplifier implemented using CMOS technology, where an NMOS transistor is used as the main amplifying device and a PMOS transistor acts as an active load.
In this circuit, M1 (CMOSN) is the NMOS transistor that receives the input signal. The input voltage (Vin) is applied to its gate through the source V3, which is a small sinusoidal signal. The source of M1 is connected to ground through a resistor R1 (1kΩ), which provides stability and helps in biasing.
Above M1, there is a PMOS transistor (M2) connected to the supply voltage. This PMOS acts like a load instead of a simple resistor, which improves the gain of the amplifier. The gate of M2 is biased using a DC voltage source (V4), so it operates in the correct region.
The output voltage (Vout) is taken from the node between M1 and M2. When the input signal at the gate of M1 changes, it controls the current flowing through M1. This change in current affects the voltage at the drain, which is the output and output signal is inverted. So, when the input increases, the output decreases, and vice versa.

* M1 (NMOS) → amplifies the input signal
* M2 (PMOS) → acts as an active load
* R1 → provides source degeneration and stability
* Vout → output is taken from the drain nod

### Input Signal
The input voltage is defined as:

SINE(0.81 10m 1000)

Where:
0.81 V = DC offset
10 mV = Amplitude of the input signal
1000 Hz = Frequency of the signal
### Circuit Operation
The given circuit operates as a Common Source (CS) amplifier with source degeneration and an active load using CMOS transistors.
In this configuration, the NMOS transistor (M1) acts as the main amplifying device, while the PMOS transistor (M2) functions as an active load. The circuit is properly biased using DC voltage sources to ensure that both transistors operate in the saturation region, which is necessary for amplification.
When an input signal is applied to the gate of the NMOS transistor, it causes a variation in the gate-to-source voltage (Vgs). This variation directly affects the drain current (Id) flowing through M1. As the input voltage increases, the drain current increases, and as the input decreases, the drain current decreases.
The PMOS transistor, acting as a load, converts these current variations into corresponding voltage variations at the output node. Since the PMOS provides a relatively high effective resistance, even small changes in current result in significant changes in output voltage.

The resistor connected at the source of the NMOS introduces source degeneration, which enhances the stability of the circuit, improves linearity, and reduces distortion by providing negative feedback.
The output is taken from the common node between M1 and M2. Due to the nature of operation, the circuit produces an inverted output, meaning that an increase in input voltage results in a decrease in output voltage, and vice versa.Thus, the circuit effectively performs voltage amplification with improved gain and stability compared to a simple resistive-load CS amplifier.

### Design Calculations :
### 1. Drain Current (ID)
For the NMOS transistor operating in saturation region:

ID = (1/2) * μn * Cox * (W/L)n * (VGS − VTN)^2

Where:
Given Specifications:

VDD = 2 V

ID = 200 µA

VOV = 0.25 V

CL = 1 pF

Ln = Lp = 180 nm

P<= 1.2mW

εr = 3.9

ε0 = 8.854 × 10⁻¹² F/m

tox = 4.1 × 10⁻⁹ m

μn = 273.809 cm²/Vs

μp = 115.689 cm²/Vs
μn = Electron mobility
Cox = Oxide capacitance per unit area
(W/L)n = Aspect ratio of NMOS transistor
VGS = Gate to source voltage
VTN = Threshold voltage of NMOS Given Specifications:
μp = 115.689 cm²/Vs
Power constraint:Assuming ID =200µA which satisfy P<=1.2mW (P=V*I ; 2×200×10^−6 ; 400µW<=1.2mW)

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
 Output Voltage Selection
For symmetrical output swing:

Vout = VDD/2 + VRS

Vout = 1 + 0.2

Vout = 1.2 V

5.3: Overdrive Voltage
Assume:

VOV = 0.25 V VTH = 0.36 V

VOV = VGS - VTH

VGS = VOV + VTH

VGS = 0.25 + 0.36

VGS = 0.61 V

5.4: Gate Voltage
VG = VGS + ID RS

Assume:

VRS = 0.2 V

VG = 0.61 + 0.2

VG = 0.81 V

5.5: Source Resistor
RS = VRS / ID

RS = 0.2 /200µ

RS = 1k Ω

5.6: NMOS Width Calculation
Drain current equation:

ID = (1/2) kn' (W/L) (VOV)^2

Where

kn' = μn Cox

μn = 273.81 cm²/Vs

Cox = εox / tox

εox = 8.854 × 10⁻¹² × 3.9

tox = 4.1 × 10⁻⁹

kn' = 2.306 × 10⁻⁴

Now solving for W:

W = 5 µm

Thus

Wn = 5 µm

5.7: PMOS Gate Bias
For PMOS: VOV = VSG − |VTP| Assume |VTP| = 0.39 V

VSG = VOV + |VTP|

VSG = 0.25 + 0.39

VSG = 0.64 V

Since: VSG = VS − VG VS = VDD = 2 V

VG = 2 − 0.64 VG = 1.36 V

5.8: PMOS Width Calculation
Wp = (2 ID L) / (μp Cox (VOV)²)

Wp = 11.82 µm By varying width:

Wp = 34.6 µm → Id = 200 µA
Wn = 27.5 µm → Id = 200 µA
### DC operating point
![Image description](https://github.com/2024ecdeekshithagjc-bit/Experiment-no2/blob/main/DC%20operating%20point.jpeg?raw=true)

### DC sweap analysis:
![Image description](https://github.com/2024ecdeekshithagjc-bit/Experiment-no2/blob/main/DC%20sweap%20.png?raw=true)
### Simulated Results:
Voltage Gain: Av = ΔVout / ΔVin Av = (1.314-1.136) / (819.64-800)  = 12.34 V/V

Gain in decibels: Gain(dB) = 20 log10(Av) = 20 log10(12.34) = 22.67 dB


### Transient analysis:
![Image description](https://github.com/2024ecdeekshithagjc-bit/Experiment-no2/blob/main/transient%20analysis1.png?raw=true)

### Theoritical Results:
Small-signal Voltage Gain: Av = gm × RD = (1.6 × 10⁻³) × (5 × 10³) = 3.70

Gain in decibels: Gain(dB) = 20 log10(Av) = 20log(3.70) = 11.36 dB

gm = 2ID / VOV

gm = (2 × 200 × 10⁻⁶) / 0.25

gm = 1.6 × 10⁻³ S

ro = 1 / (λ ID)

ro = 1 / (0.1 × 200 × 10⁻⁶)

ro = 50 kΩ

(ro1 || ro2) = 25 kΩ

Av = - gm (ro1 || ro2) / (1 + gm RS) Av = - (1.6 × 10⁻³ × 25 × 10³) / (1 + 1.6 × 10⁻³ × 1 × 10³) Av = -40 / 2.6

Av = -15.38 V/V

Av(dB) = 20 log(15.38)

Av(dB) = 23.74 dB
### AC analysis:
![Image description](https://github.com/2024ecdeekshithagjc-bit/Experiment-no2/blob/main/AC%20analysis%201.png?raw=true)
The **bandwidth** of the amplifier represents the range of frequencies over which the circuit can effectively amplify the input signal. It is calculated as the difference between the upper cutoff frequency ((F_H)) and the lower cutoff frequency ((F_L)). Based on the analysis, the bandwidth of the designed amplifier is approximately **191.095 MHz**, which indicates that the circuit is capable of operating over a wide range of frequencies.

When the theoretical calculations are compared with the simulation results, a small difference can be observed. The **theoretical voltage gain** of the amplifier is calculated to be **15.38 V/V**, whereas the **simulated voltage gain** obtained from the simulation is **14.37 V/V**. Similarly, the **gain in decibels** is theoretically estimated as **23.74 dB**, while the simulated result shows a slightly lower value of **22.612 dB**.

These differences occur because theoretical calculations usually consider ideal conditions, whereas simulations include more practical factors such as device parameters, internal resistances, and non-ideal transistor behavior. Overall, the simulated results are reasonably close to the theoretical values, which confirms that the amplifier design works as expected.
### transient analysis:
The graph shows the transient response of a CMOS amplifier, where the green waveform represents the input signal (V_{in}) and the blue waveform represents the output signal (V_{out}). The input is a small sinusoidal signal applied around a DC bias point (approximately 0.8 V), which allows the MOSFET to operate in its active region. As this small AC signal is fed into the gate of the NMOS transistor, it controls the drain current. Variations in this current cause corresponding voltage changes at the output node, resulting in an amplified version of the input signal. The output waveform clearly has a much larger amplitude compared to the input, indicating that the circuit is providing voltage gain. The output is also centered around a higher DC level due to the biasing conditions of the circuit.

From the graph, the input voltage varies approximately between 0.80 V and 0.82 V, giving a peak-to-peak input voltage of about **0.02 V (20 mV)**. The output voltage varies roughly between 1.05 V and 1.32 V, resulting in a peak-to-peak output voltage of about **0.27 V (270 mV)**. This shows that the amplifier increases the signal amplitude significantly while maintaining the sinusoidal shape, which confirms proper linear amplification.
### Unity Gain Bandwidth Product:
f(0dB) = 3.066 GHz

UGB = Av × BW

UGB = 12.387 × 191.095 MHz

UGB = 2367.09 MHz

UGB = 2.367 GHz
### Inference
The difference between theoretical and simulated results occurs due to practical MOSFET non-idealities such as channel length modulation, mobility degradation, and parasitic capacitances.
These non-ideal effects introduce a dominant pole that limits the high-frequency response of the amplifier.
Source degeneration slightly reduces the gain but improves the stability and linearity of the circuit.
Overall, the amplifier performance remains close to the expected theoretical results.

### CONFIGURATION - 2b : Cascode Amplifier
### 1. Aim:
Design CS Amplifier using NMOSFET in tsmc 180nm using VDD=2V, P<=1.5mW, C=1pF, Ln=560nm

### 2. Circuit:
![Image description](https://github.com/2024ecdeekshithagjc-bit/Experiment-no2/blob/main/circuit2.png?raw=true)
DC Analysis:
Given Specifications:

VDD = 2 V

ID = 200 µA

VOV = 0.25 V

CL = 1 pF

Ln = Lp = 180 nm

P<= 1.2mW

εr = 3.9

ε0 = 8.854 × 10⁻¹² F/m

tox = 4.1 × 10⁻⁹ m

μn = 273.809 cm²/Vs

μp = 115.689 cm²/Vs

## 2.1 Power constraint:
Assuming ID =200µA which satisfy P<=1.2mW (P=V*I ; 2×200×10^−6 ; 400µW<=1.2mW)

## 2.2: Output Voltage Selection
For symmetrical output swing:

Vout = VDD/2

Vout = 2/2

Vout = 1 V

## 2.3 For M1 (NMOS) transistor :
VOV = 0.25V and VTH = 0.36V

VS1 = VD3

We know that, VDS3 >= VOV

Hence, VD3 = VS1 = 0.3 V

Vin = VG1 = VS1 + VGS1 = 0.3 + 0.61 = 0.91 V

For M1 to be SATURATION,
VGS1 >= VTH

0.61 V >= 0.36 V

also VDS1 >= VOV

VDS1 = VD1 - VS1 = Vout - VS1 = 1 - 0.3 = 0.7 V

Hence, 0.7 V >= 0.25 V

Both the conditions are satisfied, M1 is operating in saturation region.

2.4 For M3 (NMOS) transistor:
VOV = 0.25V, VTH = 0.36V

VGS3 = VOV + VTH = 0.25 + 0.36

VGS3 = 0.61V

so VB2 = 0.61V

For M3 to be SATURATION,
VGS3 >= VTH

0.61 V >= 0.36 V

also VDS3 >= VOV

VDS = 0.33 V from the simulation

Hence, 0.33 >= 0.25

Both the conditions are satisfied. M3 is operating in SATURATION region.

## 2.5 For M2 (PMOS) transistor:
VOV = 0.25V, VTH = 0.39V

VSG2 = VOV + |VTH|

VSG2 = 0.25 + 0.39

VSG2 = 0.64 V

VG2 = VS2 - VSG2

VG2 = 2 - 0.64

VG2 = 1.36 V

so VB1 = 1.36 V

For M2 to be SATURATION,
VSG2 >= |VTH|

0.64 V >= 0.36 V

also VSD2 >= VOV

VSD2 = VDD - Vout

VSD2 = 2 - 1

VSD2 = 1 V

Hence, 1 V >= 0.25 V

Both the conditions are satisfied. M2 is operating in SATURATION region.

2.6 Drain current equation for M1 and M3 transistor:
ID = (1/2) kn' (W/L) (VOV)^2

Where

kn' = μn Cox

μn = 273.81 cm²/Vs

Cox = εox / tox

εox = 8.854 × 10⁻¹² × 3.9

tox = 4.1 × 10⁻⁹

kn' = 2.306 × 10⁻⁴

Now solving for W:

W = 5 µm

Thus

W1 = 5 µm

similarly, W3 = 5 µm

2.7 Drain current equation for M2 transistor:
ID = (1/2) kn' (W/L) (VOV)^2

W2 = 11.82 µm

By varying width:

W1 = 25 µm → Id = 200 µA
W2 = 34.605 µm → Id = 200 µA
W3 = 15.79 µm → Id = 200 µA
### 3. DC Operating Point before modifying the width:
![Image description](https://github.com/2024ecdeekshithagjc-bit/Experiment-no2/blob/main/Dc%20op%202.png?raw=true)
### 4.DC Operating Point after modifying the value of width:
![Image description](https://github.com/2024ecdeekshithagjc-bit/Experiment-no2/blob/main/DC%20operating%20point%202.png?raw=true)
### DC sweep:
![Image description](https://github.com/2024ecdeekshithagjc-bit/Experiment-no2/blob/main/DC%20sweep%202.png?raw=true)
### Transient analysis:
![Image description]()










 


