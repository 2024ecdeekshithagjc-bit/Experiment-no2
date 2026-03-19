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
![Image description](https://github.com/2024ecdeekshithagjc-bit/Experiment-no2/blob/main/cs%20amplifier%20with%20load%20resistor.png?raw=true)

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
![Image description]()
The **bandwidth** of the amplifier represents the range of frequencies over which the circuit can effectively amplify the input signal. It is calculated as the difference between the upper cutoff frequency ((F_H)) and the lower cutoff frequency ((F_L)). Based on the analysis, the bandwidth of the designed amplifier is approximately **191.095 MHz**, which indicates that the circuit is capable of operating over a wide range of frequencies.

When the theoretical calculations are compared with the simulation results, a small difference can be observed. The **theoretical voltage gain** of the amplifier is calculated to be **15.38 V/V**, whereas the **simulated voltage gain** obtained from the simulation is **12.39 V/V**. Similarly, the **gain in decibels** is theoretically estimated as **23.74 dB**, while the simulated result shows a slightly lower value of **21.86 dB**.

These differences occur because theoretical calculations usually consider ideal conditions, whereas simulations include more practical factors such as device parameters, internal resistances, and non-ideal transistor behavior. Overall, the simulated results are reasonably close to the theoretical values, which confirms that the amplifier design works as expected.
### Inference
The difference between theoretical and simulated results occurs due to practical MOSFET non-idealities such as channel length modulation, mobility degradation, and parasitic capacitances.
These non-ideal effects introduce a dominant pole that limits the high-frequency response of the amplifier.
Source degeneration slightly reduces the gain but improves the stability and linearity of the circuit.
Overall, the amplifier performance remains close to the expected theoretical results.

### CONFIGURATION - 2
### Circuit :
The circuit represents a common source amplifier with active load implemented using CMOS transistors in TSMC 0.18 µm technology.

M1 (NMOS) acts as the main amplifying transistor. The input signal Vin is applied to its gate through the voltage source V4, which is defined as SINE(0.91 10m 1k).
M2 (PMOS) works as an active load transistor and is connected to the supply voltage V1 = 2 V. Its gate is biased using V3 = 2 V to maintain proper operating conditions.
M3 (NMOS) functions as a current source / bias transistor. The gate of M3 is biased with V5 = 0.61 V to set a constant current through the amplifier branch.
The output voltage (Vout) is taken at the drain node of M1 and M2.
V2 = 1.36 V is used to provide an additional biasing condition for proper transistor operation.
The circuit includes different analyses:
.op for operating point analysis
.dc V4 0 2 for DC sweep of the input
.tran 5m for transient response
.ac dec 10 0.1 100G for frequency response analysis

### Calculations :
Given Specifications:

VDD = 2 V ID = 200 µA VOV = 0.25 V CL = 1 pF Ln = Lp = 180 nm P<= 1.5mW εr = 3.9 ε0 = 8.854 × 10⁻¹² F/m tox = 4.1 × 10⁻⁹ m μn = 273.809 cm²/Vs μp = 115.689 cm²/Vs

Power constraint:
Assuming ID =200µA which satisfy P<=1.5mW (P=V*I ; 2×200×10^−6 ; 400µW<=1.5mW)

Output Voltage Selection
For symmetrical output swing:

Vout = VDD/2 Vout = 2/2 Vout = 1 V

For M1 (NMOS) transistor :
VOV = 0.25V and VTH = 0.36V VS1 = VD3 We know that, VDS3 >= VOV Hence, VD3 = VS1 = 0.3 V Vin = VG1 = VS1 + VGS1 = 0.3 + 0.61 = 0.91 V

For M1 to be SATURATION, VGS1 >= VTH 0.61 V >= 0.36 V also VDS1 >= VOV VDS1 = VD1 - VS1 = Vout - VS1 = 1 - 0.3 = 0.7 V Hence, 0.7 V >= 0.25 V Both the conditions are satisfied, M1 is operating in saturation region.
For M3 (NMOS) transistor:
VOV = 0.25V, VTH = 0.36V

VGS3 = VOV + VTH = 0.25 + 0.36 VGS3 = 0.61V so VB2 = 0.61V

For M3 to be SATURATION, VGS3 >= VTH 0.61 V >= 0.36 V also VDS3 >= VOV VDS = 0.33 V from the simulation Hence, 0.33 >= 0.25 Both the conditions are satisfied. M3 is operating in SATURATION region.
For M2 (PMOS) transistor:
VOV = 0.25V, VTH = 0.39V VSG2 = VOV + |VTH| VSG2 = 0.25 + 0.39 VSG2 = 0.64 V VG2 = VS2 - VSG2 VG2 = 2 - 0.64
VG2 = 1.36 V so VB1 = 1.36 V

For M2 to be SATURATION, VSG2 >= |VTH| 0.64 V >= 0.36 V also VSD2 >= VOV VSD2 = VDD - Vout
VSD2 = 2 - 1 VSD2 = 1 V Hence, 1 V >= 0.25 V
Both the conditions are satisfied. M2 is operating in SATURATION region.

Drain current equation for M1 and M3 transistor:
ID = (1/2) kn' (W/L) (VOV)^2 Where kn' = μn Cox μn = 273.81 cm²/Vs Cox = εox / tox εox = 8.854 × 10⁻¹² × 3.9 tox = 4.1 × 10⁻⁹ kn' = 2.306 × 10⁻⁴ Now solving for W: W = 5 µm Thus W1 = 5 µm similarly, W3 = 5 µm

Drain current equation for M2 transistor:
ID = (1/2) kn' (W/L) (VOV)^2

W2 = 11.82 µm

By varying width:

W1 = 25 µm → Id = 200 µA
W2 = 34.605 µm → Id = 200 µA
W3 = 15.79 µm → Id = 200 µA

### Simulated Results:
Vin(p-p) = Vin (max) − Vin (min) = 919.61 mV - 900.39 mV

Vin(p-p) = 19.22 mV

Vout(p-p) = Vout (max) − Vout (min) = 1.03 V - 967.25 mV

Vout(p-p) = 62.75 mV Voltage Gain:

Av = ΔVout / ΔVin Av = 62.75/ 19.22 Av = 3.26 V/V

Gain in decibels:

Gain(dB) = 20 log10(Av) = 20log(3.26) Av(dB) = 10.26 dB

### Theoritical Results:
gm1 = 2ID / VOV gm1= (2 × 200 × 10⁻⁶) / 0.25 gm1 = 1.6 × 10⁻³ S ro = 1 / (λ ID) ro = 1 / (0.1 × 200 × 10⁻⁶) ro1 = 50 kΩ

similarly, ro2 = 50 kΩ , ro3 = 50 kΩ

(ro1 || ro2) = 25 kΩ Av = -gm1 (ro1 || ro2) / (1 + gm1 · ro3) AV = - 0.5 V/V Av(dB) = 20 log(Av) = 20 log(0.5) = 6.020 dB

Voltage Gain: The measured voltage gain of the amplifier is found to be

Av = 10.87 - 3 = 7.87 dB
Cutoff Frequency: The frequency at which the gain drops to the −3 dB level is observed as

### Upper cutoff frequency:

fH = 110.529 MHz

### Lower cutoff frequency:

fL ≈ 0

Bandwidth:

BW = FH − FL

BW = 110.529 MHz

The **Gain Bandwidth Product (GBP)** is an important parameter used to evaluate the performance of an amplifier. It represents the product of the voltage gain ((A_v)) and the bandwidth ((BW)) of the circuit. In this design, the gain bandwidth product is calculated by multiplying the gain **3.49** with the bandwidth **110.529 MHz**, which gives a value of approximately **385.71 MHz** or **0.385 GHz**.

When the theoretical and simulated results are compared, a difference can be observed. The **theoretical voltage gain** is **0.5 V/V**, while the **simulated gain** is **3.26 V/V**. Similarly, the **theoretical gain in decibels** is **6.020 dB**, whereas the **simulated value** is **10.26 dB**. This variation occurs because theoretical calculations assume ideal conditions, while simulation results include practical effects of the devices and circuit parameters.

### Result:
The Common Source (CS) amplifier that uses a resistive load along with source degeneration shows a lower voltage gain compared to a conventional CS amplifier. Simulation results indicate that although the peak-to-peak output amplitude is slightly reduced, the circuit produces a more linear output signal and maintains a more stable operating point even when MOSFET parameters vary.

### Validation
The simulation confirms the theoretical gain equation:

Av = -(gm × RD) / (1 + gm RS)

The simulated gain is close to the calculated value. The output waveform is inverted by 180° relative to the input, which is a characteristic property of a common-source amplifier. A small AC component at the source node indicates the presence of negative feedback in the circuit.

### Inference
The inclusion of M3 introduces negative feedback in the circuit, which enhances the stability of the amplifier operation. This feedback mechanism allows the amplifier to handle larger input signals with reduced distortion. Even though source degeneration decreases the voltage gain, it improves bias stability and linear behavior. Therefore, a balanced design must consider both feedback and output impedance to maintain adequate gain and bandwidth.

### CONFIGURATION - 3
Circuit Description
The circuit represents a common source (CS) amplifier with source degeneration and active load implemented using CMOS transistors with TSMC 0.18 µm technology.

M1 (NMOS) acts as the main amplifying transistor. The input signal Vin is applied to its gate through the voltage source V4, which is defined as SINE(1.22 10m 1k) for transient analysis and AC 1 for AC analysis.

M2 (PMOS) functions as the active load for the amplifier. It is connected to the supply voltage V1 = 2 V, and its gate is biased using V2 = 2 V to maintain proper operation.

M3 (NMOS) acts as a current source / bias transistor. Its gate is biased using V3 = 1.36 V, which helps establish a constant current through the amplifier branch.

The output voltage (Vout) is taken at the drain node of M1 and M2.

The circuit includes different analyses:

.op – Determines the DC operating point of the circuit.

.dc V4 0 2 – Performs DC sweep analysis of the input voltage.

.tran 5m – Performs transient analysis to observe the time-domain response.

.ac dec 10 10 100G – Performs AC analysis to study the frequency response of the amplifier.

### Calculations :
Given Specifications: VDD = 2 V ID = 200 µA VOV = 0.25 V CL = 1 pF Ln = Lp = 180 nm P<= 1.5mW εr = 3.9 ε0 = 8.854 × 10⁻¹² F/m tox = 4.1 × 10⁻⁹ m μn = 273.809 cm²/Vs μp = 115.689 cm²/Vs

### Power constraint:
Assuming ID =200µA which satisfy P<=1.5mW (P=V*I ; 2×200×10^−6 ; 400µW<=1.5mW)

### Output Voltage Selection
For symmetrical output swing: Vout = VDD/2 Vout = 2/2 Vout = 1 V

For M1 (NMOS) transistor :
VOV = 0.25V and VTH = 0.36V VGS1 = VOV + VTH = 0.25 + 0.36
VGS1 = 0.61V VS1 = 0.61 V Vin = VS1 + VGS1 Vin = 0.61 + 0.61 Vin = 1.22 V so, VG1 = 1.22 V

For M1 to be SATURATION, VGS1 >= VTH 0.61 V >= 0.36 V also VDS1 >= VOV
VDS1 = VD1 - VS1 = Vout - VS1 = 1 - 0.61

VDS1 = 0.39 V Hence, 0.39 V >= 0.25 V Both the conditions are satisfied, M1 is operating in saturation region.

For M3 (NMOS) transistor:
VOV = 0.25V, VTH = 0.36V

VG3 = VS1 VGS3 = VOV + VTH = 0.25 + 0.36 VGS3 = 0.61V so, VG3 = 0.61V For M3 to be SATURATION, VGS3 >= VTH 0.61 V >= 0.36 V also VDS3 >= VOV VDS = 0.606 V from the simulation Hence, 0.606 >= 0.25 Both the conditions are satisfied. M3 is operating in SATURATION region

For M2 (PMOS) transistor:
VOV = 0.25V, VTH = 0.39V VSG2 = VOV + |VTH| = 0.25 + 0.39 VSG2 = 0.64 V VG2 = VS2 - VSG2 = 2 - 0.64 VG2 = 1.36 V so VB1 = 1.36 V For M2 to be SATURATION, VSG2 >= |VTH| 0.64 V >= 0.36 V also VSD2 >= VOV VSD2 = VDD - Vout VSD2 = 2 - 1 VSD2 = 1 V Hence, 1 V >= 0.25 V Both the conditions are satisfied. M2 is operating in SATURATION region.

### Drain current equation for M1 and M3 transistor:
ID = (1/2) kn' (W/L) (VOV)^2 Where kn' = μn Cox μn = 273.81 cm²/Vs Cox = εox / tox εox = 8.854 × 10⁻¹² × 3.9 tox = 4.1 × 10⁻⁹ kn' = 2.306 × 10⁻⁴ Now solving for W: W = 5 µm Thus W1 = 5 µm similarly, W3 = 5 µm

### Drain current equation for M2 transistor:
ID = (1/2) kn' (W/L) (VOV)^2 W2 = 11.82 µm By varying width:

W1 = 14.8 µm → Id = 200 µA
W2 = 35 µm → Id = 200 µA
W3 = 14.9 µm → Id = 200 µA
Simulated Results:
Vin(p-p) = Vin (max) − Vin (min) = 1.22 V - 1.21 V Vin(p-p) = 0.01 V Vout(p-p) = Vout (max) − Vout (min) = 1.21 V - 0.869 V Vout(p-p) = 0.341 V

Voltage Gain: Av = ΔVout / ΔVin Av = 0.341/ 0.01 Av = 34.1 V/V Gain in decibels: Gain(dB) = 20 log10(Av) = 20log(34.1) Av(dB) = 30.65 dB

### Theoritical Results:
gm1 = 2ID / VOV gm1= (2 × 200 × 10⁻⁶) / 0.25 gm1 = 1.6 × 10⁻³ S ro = 1 / (λ ID) ro = 1 / (0.1 × 200 × 10⁻⁶) ro1 = 50 kΩ similarly, ro2 = 50 kΩ ro3 = 1/gm (ro1 || ro2) = 25 kΩ Av = -gm1 (ro1 || ro2) / (1 + gm1 . 1/gm) AV = -20 V/V Av(dB) = 20 log(20) = 20 log(0.5) = 26.02 dB

 Voltage Gain: The measured voltage gain of the amplifier is found to be Av = 25.195 - 3 = 22.195 dB
Cutoff Frequency: The frequency at which the gain drops to the −3 dB level is observed as

Upper cutoff frequency: fH = 345.989 MHz
Lower cutoff frequency: fL ≈ 0
Bandwidth:

BW = FH − FL BW =345.989 MHz

### Gain Bandwidth Product:
GBP = Av × BW GBP = 18.182 × 345.989 MHz GBP = 6363.49 MHz










 


