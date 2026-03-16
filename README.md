# Experiment-no2
Design the mpliefier confuguration using tsmc in LTSPICE

## Amplifier Configurations Implemented

### 1. Common Source Amplifier with Source Degeneration

In this configuration, a resistor is connected in series with the 
source terminal of the NMOS transistor. This resistor provides 
negative feedback which improves the stability and linearity of 
the amplifier. Source degeneration also helps in controlling the 
gain and reducing distortion in the output signal.

- Improved linearity
- Better bias stability
- Reduced voltage gain compared to basic CS amplifier


### 2. Cascode Amplifier

The cascode amplifier is formed by stacking two transistors, where 
the lower transistor operates as a common source stage and the 
upper transistor acts as a common gate stage.

This configuration significantly improves the output resistance 
and increases the overall voltage gain while reducing the effect 
of parasitic capacitances.

- High voltage gain
- Improved bandwidth
- Reduced Miller effect

### 3. Current Mirror Loaded Common Source Amplifier

In this design, an active load is implemented using a current mirror 
instead of a passive resistor. The current mirror provides a high 
output resistance which leads to an increased voltage gain.

This configuration is commonly used in integrated circuit amplifier 
designs because it allows efficient current biasing and improved 
amplification.

- Higher gain due to active load
- Efficient biasing using current mirrors
- Widely used in analog IC design


## Types of Analysis Performed

### DC Analysis
DC analysis is carried out to determine the operating point (Q-point) 
of the amplifier. It verifies that the NMOS transistor is operating 
in the saturation region for proper amplification.

### Transient Analysis
Transient simulation is used to observe the time-domain behavior of 
the amplifier. It shows how the output signal responds to an input 
signal over time.

### AC Analysis
AC analysis is performed to evaluate the frequency response of the 
amplifier. It helps determine parameters such as voltage gain, 
bandwidth, and cutoff frequencies

## Software Tools Used

- LTspice for circuit simulation
- TSMC 180nm Technology Library
- MATLAB for documentation and signal analysis (if required)

## Applications

Common Source amplifiers are widely used in:

- Analog integrated circuits
- Audio amplification systems
- Sensor signal conditioning
- Communication circuits

## Summary

This project demonstrates the design and performance evaluation of 
different Common Source amplifier topologies using NMOS transistors 
in 180 nm CMOS technology. By performing DC, transient, and AC 
simulations, the behavior and advantages of each configuration 
can be clearly understood.
