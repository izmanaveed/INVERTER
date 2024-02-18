# INVERTER

## PROBLEM STATEMENT
Design and implement an inverter circuit to meet the following load specifications. 
- Current = 1 A
- Voltage= 220 V
- Sine wave having frequency = 50 Hz
- THD = 10%
- Overcharging protection of battery
- Design with minimal complexity is preferred

## PROJECT OBJECTIVES
This project has 2 objectives which serve as a guideline to achieve the desired result. The objectives are:
1. To design a pure sine wave inverter that gives ac output of 220V.
2. Proper safety features should be implemented in the inverter.

## BLOCK DIAGRAM 
![image](https://github.com/izmanaveed/INVERTER/assets/59065717/9ddbb31f-cd76-4d0d-b2e6-721c1666c720)

## EQUIPMENT USED
- Arduino Nano
- IC 7404
- 7809 Voltage Regulator
- IRF 540
- BC548
- 1K and 10K resistors (x2 each)
- Step up transformer (12V to 220V)
- Power supply
- 0.uF capacitor (x2)

## WORKING 
![image](https://github.com/izmanaveed/INVERTER/assets/59065717/2c06780e-1a85-44d6-937e-f45446592b18)
As this signal has a very weak current, it is amplified by a BC 547 transistor.
The amplified signal is given at the gates of M1 and M2 MOSFETs.
The output of the microcontroller is given to another BC 547 which is working as an inverting amplifier.
By this, the signal from the microcontroller gets inverted as well as amplified.
This signal is given at the gates of M3 and M4 MOSFETs.
Now what happens is that, when the input signal at the gate of M1 is high and at the gate of M4 is low, conduction from M1-M4 occurs and we achieve a +12V signal.
When the input signal at the gate of M3 goes high and at the gate of M2 goes low, conduction from M3-M2 occurs and we achieve a -12V signal.
Thus, at the output, we receive a waveform of 12Vpeak or 24Vpeak-peak.
This output is then fed into a transformer which steps up this 12 Volts AC waveform into 220Volts AC.
The Arduino is the heart of the circuit as it generates a 50Hz square wave at a 50% duty cycle.
The two BC548 are the buffers for MOSFET IRF540N. The IRF540N or most of the MOSFETs need 10V to fully turn on, but the Arduino pins deliver only 5V.
The two BC548 take the low voltage (5V Signal) from Arduino and deliver 12V at the “gate” terminal, which is sufficient for turn the MOSFETs fully ON.
If the MOSFET is not fully ON there will be resistance between Source and Drain Terminal, which generates heat and affects the output voltage and current.
The Arduino oscillates each MOSFET at a time energizing the secondary side winding alternately, which produces stable 50Hz 230V AC at the output.

## PROBLEMS FACED
- During the etching process, the parts of the circuit that was not covered by the permanent marker had their coper removed, thus, hampering the conduction of the circuit.
- The imprint of the butter paper was not completely transferred on the PCB board so we had to darken the imprints using a permanent marker.
- After the soldering process, the PCB circuit was not functioning properly so the whole circuit had to be desold.
- Heating up of voltage regulator.
- Issues in initial PCB design.

## CONCLUSION
Our circuit was successfully implemented on breadboard however some issues were faced in the pcb circuit due to which output is not accurate. The images are enclosed below for the circuit implemented.
![image](https://github.com/izmanaveed/INVERTER/assets/59065717/92dc3232-dc20-441f-b88f-7b6af437a1d4)

### PCB: 
![image](https://github.com/izmanaveed/INVERTER/assets/59065717/b6796b6c-8577-4c4e-aaec-896212ffdd1f)
![image](https://github.com/izmanaveed/INVERTER/assets/59065717/01524f66-da7d-431a-aed1-8611a1f58fbc)

### Output without transformer:
![image](https://github.com/izmanaveed/INVERTER/assets/59065717/c292b2f6-dd73-4f20-b537-f0265ad3030f)

### Circuit:
![image](https://github.com/izmanaveed/INVERTER/assets/59065717/d4b90f56-f28b-4bbf-8b48-a506fdc6f92a)
![image](https://github.com/izmanaveed/INVERTER/assets/59065717/b8c0334a-59b2-4e32-aa0c-d702c5d920a0)



