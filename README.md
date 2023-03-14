<!--- $ git commit -m "Refactor" usability tests.
>
>
Co-authored-by: Abhishek Ranjan <abhi.ranjan5115@gmail.com> --->

# Device-Characterization-Lab

# Table of Contents
<div class="toc">
  <ul>
    <li><a href="#header-1">Week 1. Familiarization with Instrumentation</a></li>
	<ul>
        <li><a href="#header-1_1">Familiarization the functions of SMU (Source Measuring Unit)</a></li>
      </ul>
      <ul>
        <li><a href="#header-1_2">Experiement 1: Measurement of accuracy in low resistance measurement</a></li>
      </ul>
</div>

<div class="toc">
  <ul>
    <li><a href="#header-2">Week 2. Familiarization with Instrumentation</a></li>
	<ul>
        <li><a href="#header-2_1">Familiarization to Oscilloscope</a></li>
      </ul>
      <ul>
        <li><a href="#header-2_2">Experiement 2.1: Measurement of Capacitance value & Cutoff frequency from RC Filters</a></li>
      </ul>
	<ul>
        <li><a href="#header-2_3">Experiement 2.2: Measurement of Inductance value & Cutoff frequency from RL Filters</a></li>
      </ul>
	<ul>
        <li><a href="#header-2_3">Experiement 2.3: Measurement of Resonance & Cutoff frequency from RLC Filters</a></li>
      </ul>
</div>	

<div class="toc">
  <ul>
    <li><a href="#header-3">Week 3. Familiarization with Instrumentation</a></li>
	  <ul>
        <li><a href="#header-3_7">Familiarization to LCR meter</a></li>
      </ul>
	<ul>
        <li><a href="#header-3_1">Comparing values of capacitance(in RC circuit) from oscilloscope(by phase) and LCR meter</a></li>
      </ul>
      <ul>
        <li><a href="#header-3_2">Comparing values of inductance(in RL circuit) from oscilloscope(by phase) and LCR meter</a></li>
      </ul>
	<ul>
        <li><a href="#header-3_3">Comparing values of 0 ohm in SMU using triax and banana cables</a></li>
      </ul>
      <ul>
        <li><a href="#header-3_4">Measuring the values of Ceramic Capacitor and Electrolytic capacitor using LCR meter</a></li>
      </ul>
	<ul>
        <li><a href="#header-3_5">Solving error of week1</a></li>
      </ul>
</div>	
	
* [Week 4: MOSFET Characterisation](#week-4-mosfet-characterisation)
	- [MOS I-V Characterstics](#mos-i-v-characterstics)
	- [ERROR:](error)
* [Week 5: IRF640N MOSFET Characterisation](#week-5-mosfet-characterisation)
	- [Device Analyzer B1500](#Device-Analyzer-B1500)
	- [MOSFET Id-Vg Characterstics ](#MOSFET-Id-Vg-Characterstics)
	- [MOSFET I-Vd Characterstics](#MOSFET-Id-Vd-Characterstics)
	- [MOSFET log(Id)-Vg Characterstics](#MOSFET-log(Id)-Vg-Characterstics)
	- [MOSFET gm-Vg Characterstics](#MOSFET-gm-Vg-Characterstics)
	- [MOSFET Hf-CV Characterstics](#MOSFET-Hf-CV-Characterstics)
* [Week 6: CD4007 MOSFET Characterisation](#week-6-mosfet-characterisation)
	- [nMOS Id-Vg Characterstics ](#nMOS-Id-Vg-Characterstics)
	- [nMOS log(Id)-Vg Characterstics](#nMOS-log(Id)-Vg-Characterstics)
	- [nMOS gm-Vg Characterstics](#nMOS-gm-Vg-Characterstics)
	- [Calculation of threshold voltage](#Calculation-of-threshold-voltage)
	- [nMOS Id-Vg for varing Vb Characterstics](#nMOS-Id-Vg-for-varing-Vb-Characterstics)
	- [nMOS I-Vd Characterstics](#nMOS-Id-Vd-Characterstics)
	- [nMOS Hf-CV Characterstics](#nMOS-Hf-CV-Characterstics)
* [Week 7: CD4007 MOSFET Characterisation](#week-7-mosfet-characterisation)
	- [pMOS Id-Vg Characterstics ](#pMOS-Id-Vg-Characterstics)
	- [pMOS log(Id)-Vg Characterstics](#pMOS-log(Id)-Vg-Characterstics)
* [Week 8: MOSFET Characterisation and LDR](#Week-8-MOSFET-Characterisation-and-LDR)
	- [In Id-Vg why we got high current at negative voltage of CD4007](#In-Id-Vg-why-we-got-high-current-at-negative-voltage-of-CD4007)
	- [Designing Inverter of CD4007 IC](#Designing-Inverter-of-CD4007-IC)
	- [Light Dependent Resistor](#Light-Dependent-Resistor)

<div class="toc">
  <ul>
    <li><a href="#header-r">References</a></li>
  </ul>
</div>

<div class="toc">
  <ul>
    <li><a href="#header-r">Acknowledgement</a></li>
  </ul>
</div>

# <h1 id="header-1">Week 1. Familiarization with Instrumentation</h1> 
## <h1 id="header-1_1">Familiarization the functions of SMU (Source Measuring Unit)</h1> 
### SMU (Source Measuring Unit)
Source Measurement Unit (SMU) instrument integrates the capabilities of a precision power supply (PPS) with those of a high-performance digital multimeter (DMM) in a single instrument.
SMUs’ 2 simultaneous operation provides for faster test times, simplified connections, improved accuracy, less complex programming, and a lower cost of ownership (COO). Their tight integration lets them protect the device under test (DUT) from damage due to accidental overloads, thermal runaway, and other dangers. It also makes SMU instruments ideal for characterizing and testing semiconductors and other non-linear devices and materials.


![image](https://user-images.githubusercontent.com/120498080/211479161-ec3d1c5f-1b96-4431-9d65-f25286392091.png)

### Power line Cycle
NPLC (Number of Power Line Cycles) NPLC stands for Number of Power Line Cycles. NPLC is a measurement term that indicates the accuracy with which a voltage or current is displayed on a device such as a digital multimeter. When determining the value of a DC signal, AC noise is often present by power lines.

NPLC is number of power line cycles.  DC Voltage, DC Current, and Resistance measurement resolution, accuracy is reduced by power line induced AC noise.  Using NPLC of 1 or greater increases AC noise integration time, and increases measurement resolution and accuracy, however the trade-off is slower measurement rates.  For highest measurement accuracy NPLC of 100 is recommended.



<h1 id="header-1_2">Experiement 1 - Measurement of accuracy in low resistance measurement</h1>


**Equipments Required:**

- Low Resistance (selected resistance = 0 ohms with precision of ±0.1 ohm)
- Multimeter
- Banana Cables
- SMU (Keithley 2450)

**Procedure:**

Step 1: Identify the color codes and find out the resistance value.


 ![image](https://user-images.githubusercontent.com/120498080/211479456-7f3024a3-a3fc-4f6d-8cdd-6abd2ec06ad8.png)

- As per the colour coding the value of resistance is 0 ohms.

**Step2:** Use a multimeter and measure the resistance value 

- After measuring the value of resistance, we observe 0.1 ohm 

**Step3:** Use 2 probe and 4probe methods and measure the resistance value using Keithley 2450 Source meter (Manually)

1.Sourcing Voltage (Source = 50 mV), Limit to Current = 200 mA
	
![image](https://user-images.githubusercontent.com/120498080/214098275-613b1a64-d9eb-401e-b2de-bb770662a8dc.png)

2. Sourcing Current (Source = 200 mA), Limit to Voltage = 50 mV
	
![image](https://user-images.githubusercontent.com/120498080/214098496-cb7b1de0-824c-45cb-9595-905b078ce3e5.png)

### Programme and SMU
**Step 4:** Using 4probe method and measure the resistance value using Keithley 2450 

Source meter (Remote control via USB)
### TSP Codes :
```verilog
TSP Program: 
--TODO Please insert code here.--Reset the instrument to the default settings
reset()
--Configure the Simple Loop trigger model template to make 100 readings.
trigger.model.load("SimpleLoop", 100)
--Change the view on the front panel to the GRAPH swipe screen.
display.changescreen(display.SCREEN_GRAPH_SWIPE)
--Set to measure resistance, use 4-wire sense,
--and offset compensation.
smu.measure.func = smu.FUNC_RESISTANCE
smu.measure.sense = smu.SENSE_4WIRE
smu.measure.offsetcompensation = smu.ON
--Turn on the output
smu.source.output = smu.ON
--Initiate trigger model and wait until finished.
trigger.model.initiate()
waitcomplete()
--Turn off output
smu.source.output = smu.OFF
--Read the resistance and time values from defbuffer1.
print("Resistance:\tTime:")
for i = 1, 100 do
print(string.format("%f\t%f", defbuffer1[i], defbuffer1.relativetimestamps[i]))
end
```
### Output Graph
![image](https://user-images.githubusercontent.com/120498080/211484172-ae254d79-8b8a-4c48-88d8-2808c68da642.png)

### SMU Output:
![image](https://user-images.githubusercontent.com/120498080/211484239-3c1c6fb9-89ae-43d3-94f7-c75eaee280bf.png)
### ERROR FACED:
- We tried to remotely control the SMU using TSB software and faced issues in auto run.

![image](https://user-images.githubusercontent.com/120498080/211484356-38fd3c98-b60e-4bbb-81bc-8bb161a292a2.png)
	
- Faced error in measuring resistance using TRIAX cable to measure resistance.


### Experiment when we use triax and BNC coverter.

# <h1 id="header-2">Week 2. Familiarization with Instrumentation</h1>
## <h1 id="header-2_1">Familiarization to Oscilloscope</h1> 
### Oscilloscope
An oscilloscope is a test & measurement instrument that rapidly measures voltage over time. It records the voltage across certain points in a circuit and displays voltage (Y-axis) as a function of time (X-axis) on a screen. It is essentially a very fast voltmeter with the capability of data-logging and plotting.
- We are using RMT2054 Oscilloscope
![download](https://user-images.githubusercontent.com/120498080/212805807-d82d6927-f737-4bb3-a4c9-ef3883904824.jpeg)


## <h1 id="header-2_2">Experiement 2.1: Measurement of Capacitance value & Cutoff frequency from RC Filters</h1> 
	
**Equipments Required:**
- Resistance and Capacitor (Resistance =  1 kΩ with precision of ±0.1 Ω and Capacitor of 0.2 uF)
- Multimeter
- BNC(Bayonet Nut Coupling) Cables
- RMT2054 Oscilloscope
- 33600A Waveform Generator
- Bread-board 

**Procedure:**
	
**Step 1:** Hand Calculation and selected components
   - Selected value of capacitance = 200 nF
   - Selected value of resistance = 1 kΩ
```
	 Cut- off frequency = 1/2πRC 
```
   - Calculated Cut-off frequency = 795 Hz
	
**Step 2:** Establishing Connections
	
![rc-low-pass-filter](https://user-images.githubusercontent.com/120498080/212807171-e3561edb-00f9-4a5a-b410-7ef7f0c6dc0e.jpg)
- We connect the R and C component in series and provide input between R and C and take output from C. 
- Applied peak to peak Voltage (Vpp = 1 V)
	
**Step 3:** Calculating the value of Capacitance using the value phase shift in input and output.
 - As we know for RC circuit, 
 ```
	tan(Φ) = ωRC
	C = tan(Φ)/(ωR)
```
	
#### The calculated values of capacitance are as follows:
	
![image](https://user-images.githubusercontent.com/120498080/214079635-5943a5ba-7cba-4d05-ab62-dc6176ddfffe.png)
 
#### Output of our RC low pass filter:
- At 500 Hz. (yellow – output, green – input)
	
![image](https://user-images.githubusercontent.com/120498080/212817642-0f1f11d4-3101-471a-9c80-467486ad63cb.png)
![image](https://user-images.githubusercontent.com/120498080/212817664-ddfa4e46-1673-4f26-a2f8-27ddd97bfe56.png)
![image](https://user-images.githubusercontent.com/120498080/212817696-142f70d9-a3a4-46e9-a408-9dd9c28b7199.png)
	
#### Output at cut-off frequency:
![image](https://user-images.githubusercontent.com/120498080/212818022-63b1c7b0-2792-4870-910f-bd788328b445.png)
![image](https://user-images.githubusercontent.com/120498080/212818055-a746f4ff-4e74-43a7-9243-3dba9933d31f.png)

**Step 4:** Plotting FFT of the output.	
	
#### FFT (Fast Fourier transform) at 500 Hz

![RC 500Hz FFT](https://user-images.githubusercontent.com/120498080/212823872-837333bb-99e1-40f9-9fb6-cb58cfab7068.PNG)
	
### Results:
- Upon observation and experimental measurements, the cut-off frequency is found out to be 2 KHz.
- The calculated value of cut-off frequency as per component rating is 795 Hz.
- The observed bandwidth of our RC value = 2 kHz.
- The calculated bandwidth of our RC value = 795 Hz.

## <h1 id="header-2_3">Experiement 2.2: Measurement of Inductance value & Cutoff frequency from RL Filters</h1>

**Equipments Required:**
- Resistance and Inductor (Resistance =  1 kΩ with precision of ±0.1 Ω and Inductor of 1 mH)
- Multimeter
- BNC(Bayonet Nut Coupling) Cables
- RMT2054 Oscilloscope
- 33600A Waveform Generator
- Bread-board

**Procedure:**
	
**Step 1:** Hand Calculation and selected components
   - Selected value of inductor = 1 mH
   - Selected value of resistance = 1 kΩ
```
	Cut- off frequency = R/2πL 
```
   - Calculated Cut – off frequency = 160 kHz

**Step 2:** Establishing Connections
	
![rl](https://user-images.githubusercontent.com/120498080/212818590-a8eac2d6-9733-479f-a095-9bac3a74208a.PNG)

- We connect the R and L component in series and provide input between R and L and output is taken across L. 
- Applied peak to peak Voltage (Vpp = 1 V)

	
**Step 3:** Calculating the value of Capacitance using the value phase shift in input and output.
 - As we know for RL circuit, 
 ```
	tan(90°-Φ) = ωL/R
	L = (R tan(90°-Φ))/(ω)
```

#### The calculated values of inductance are as follows:
	
![image](https://user-images.githubusercontent.com/120498080/214080694-34b54c97-6bf0-4b68-81c9-d0b21a480b1c.png)

#### Output of RL high pass filter:
- At 100kHz. (yellow – output, green – input)
	
![image](https://user-images.githubusercontent.com/120498080/212818999-c4519109-b2c5-4444-a84b-2c0a0d706d3d.png)
![image](https://user-images.githubusercontent.com/120498080/212819016-49a8aee4-7ce5-4df4-8bff-634ee62cdf1a.png)
![image](https://user-images.githubusercontent.com/120498080/212819031-3033e30b-e594-4bac-814d-c91a19c16006.png)

#### Output at cut-off frequency
![image](https://user-images.githubusercontent.com/120498080/212819067-0a3e333b-405a-4ab3-b323-28816441e058.png)
![image](https://user-images.githubusercontent.com/120498080/212819083-8d8244f9-b0be-42ff-b9c7-1cde1ce44ccc.png)

**Step 4:** Plotting FFT of the output.	
	
#### FFT (Fast Fourier transform) at 200 kHz.
	
![LR 200KHz FFT](https://user-images.githubusercontent.com/120498080/212823983-fcc4ccb0-39e5-4003-a94d-052c7d0f1ba0.PNG)
	
### Results:
- Upon observation and experimental measurements, the cut-off frequency is found out to be 155 kHz.
- The calculated value of cut-off frequency as per component rating is 160 kHz.
- The bandwidth of our RC value = ∞
	
## <h1 id="header-2_4">Experiement 2.3: Measurement of Resonance & Cutoff frequency from RLC Filters</h1>
**Equipments Required:**
- Resistance , Capacitor and Inductor (Resistance =  1 kΩ with precision of ±0.1 Ω , Capacitor of 0.2 uF and Inductor of 1 mH)
- Multimeter
- BNC(Bayonet Nut Coupling) Cables
- RMT2054 Oscilloscope
- 33600A Waveform Generator
- Bread-board

**Procedure:**

**Step 1:** Hand Calculation and selected components
   - Selected value of capacitance = 200 nF
   - Selected value of resistance = 1 KΩ
   - Selected value of inductor = 1 mH
   ```
	Lower Cut- off frequency = 1/2πRC
   	Higher Cut- off frequency = R/2πL
   	Resonance frequency - 1/2π√(LC)
   ```
   - Calcualted Lower Cut- off frequency = 795 Hz
   - Calcualted Higher Cut- off frequency = 160 kHz
   - Calcualted Resonance frequency - 11.25 kHz
	
**Step 2:** Establishing Connections

![rlc](https://user-images.githubusercontent.com/120498080/212835310-532cd0e4-6ebf-46ce-b613-0ad8b4e9222e.PNG)

- We connect the R, C and L component in series and provide input between L and R and output is taken across R. 
- Applied peak to peak Voltage (Vpp = 1 V)
	
**Step 3:** Observing output at different frequencies to get resonant frequency 
- Vin (pp) = 1 V
	
![image](https://user-images.githubusercontent.com/120498080/212822631-a99cb75c-221f-4729-b988-77f25dfd5f04.png)

#### Output of our LCR band pass filter:

![image](https://user-images.githubusercontent.com/120498080/212822697-9c96a3d8-020e-491f-b8d1-89aa81743ee8.png)
![image](https://user-images.githubusercontent.com/120498080/212822743-17d3428a-441f-418c-b021-3e80b5650a10.png)
![image](https://user-images.githubusercontent.com/120498080/212822768-ceec0141-1a33-4cca-a31b-d2be4558ce91.png)

**Step 4:** Observation of lead and lag in LCR circuit.

Calculated phase of  RLC circuit(by taking the value of R,C and L in transfer function): 
```
	Φ = 90° - tan-1(ω/5025) - tan-1(ω/994974)
```	
	
Before resonant frequency the output voltage across R leads the input voltage. (lower frequency range)
	
At frequency of 800 Hz: 
	- Angle per division = 11.61°
	- Change in division in input and output = 6°(lead)
	- Observed Phase = 69.67°(lead)
	- Calculated Phase = 44.70°(lead)
	
	
![image](https://user-images.githubusercontent.com/120498080/212824397-ede0cd2d-e6f8-4eb8-b7f5-7db46cd15f4e.png)

After resonant frequency the output voltage across R lags the input voltage. (higher frequency range)
At frequency of 160 kHz: 
- Angle per division = 23.22°
- Change in division in input and output = 2°(lagg)
- Observed Phase = 46.45°(lagg)
- Calculated Phase = 45°(lagg)
	
![image](https://user-images.githubusercontent.com/120498080/212824539-9a39dc6f-c520-4762-9dc3-c279fe2f13d5.png)
	
**Step 5:** Plotting FFT of the output.	
	
#### FFT (Fast Fourier transform) at 18 kHz
	
![RLC 18KHz FFT](https://user-images.githubusercontent.com/120498080/212823662-47e5f3bb-a245-42c2-bb82-a57d107b1030.PNG)
	
#### Results:
- Upon observation and experimental measurements, the resonant frequency is found out to be 18 kHz.
- The calculated value of resonant frequency as per component rating is 11.25 kHz.
- Upon observation and experimental measurements, the lower cut-off frequency is found out to be 795 Hz.
- Upon observation and experimental measurements, the higher cut-off frequency is found out to be 160 kHz.
- The calculated value of lower cut-off frequency as per component rating is 2 kHz.
- The calculated value of lower cut-off frequency as per component rating is 180 kHz.
- The observed bandwidth of our LCR value = (160 – 0.795) kHz = 159.205 kHz.
- The calculated bandwidth of our LCR value = (180 – 2) kHz = 178 kHz.
	
### Conclusion
	
There are some deviation in the measured value and actual values of capacitance and inductance, which can be due to following reasons

- The components have some errors in measured and acurate value.
- Due to wire resistance.
- Wire properties can change at differenet frequency
	
### Discussion Points :
- In function generator when we give 1Vpp then in oscilloscope it was giving 1.19Vpp sine wave - but this was fixed when we changed the BNC converter on Oscilloscope.

 
	
# <h1 id="header-3">Week 3. Familiarization with Instrumentation</h1> 
## <h1 id="header-3_7">Familiarization to LCR meter</h1>

An LCR meter is a type of electronic test equipment used to measure the inductance (L), capacitance (C), and resistance (R) of an electronic component.In the simpler versions of this instrument the impedance was measured internally and converted for display to the corresponding capacitance or inductance value. Readings should be reasonably accurate if the capacitor or inductor device under test does not have a significant resistive component of impedance. More advanced designs measure true inductance or capacitance, as well as the equivalent series resistance of capacitors and the Q factor of inductive components.

- We are using Wayne Kerr LCR meter
	
#### Wayne Kerr LCR meter
![download (91)](https://user-images.githubusercontent.com/120498080/214114552-4bac1457-f163-41ea-8020-0d49784e530b.jpeg)

- A Wayne Kerr LCR meters measures accurate and fast measurements of frequency range from 20Hz to 1MHz.
- Two test mode enables consecutive measurements to be made with two different instrument parameters set.
	
	
## <h1 id="header-3_1">Comparing values of capacitance(in RC circuit) from oscilloscope(by phase) and LCR meter</h1> 	
- Selected value of capacitance = 100 nF
- Selected value of resistance = 1 kΩ
- Calculated cut off frequency = 1.6 kHz
	
![image](https://user-images.githubusercontent.com/120498080/214089786-4ab670c6-2b00-40ce-9aea-ebdda685f116.png)

## <h1 id="header-3_2">Comparing values of inductance(in RL circuit) from oscilloscope(by phase) and LCR meter</h1>
- Selected value of inductance = 1 mH
- Selected value of resistance = 1 kΩ
- Calculated cut off frequency = 160 kHz
	
![image](https://user-images.githubusercontent.com/120498080/214082338-690abdcb-8f5d-461e-bb5e-5c85fe0af8f2.png)

## <h1 id="header-3_3">Comparing values of 0 ohm in SMU using triax and banana cables</h1>
	
1.**Sourcing Voltage** (Source = 50 mV), Limit to Current = 200 mA
- 2 wire measurment

![image](https://user-images.githubusercontent.com/120498080/214107375-e489451b-e1de-4801-bd60-db9f18bd7b63.png)

- 4 wire measurment
	
![image](https://user-images.githubusercontent.com/120498080/214106778-0cbfebaa-40cc-4473-b891-961913d29cf6.png)

2. **Sourcing Current** (Source = 200 mA), Limit to Voltage = 50 mV
- 2 wire measurment
	
![image](https://user-images.githubusercontent.com/120498080/214107026-2ea4217a-eeb6-4c9a-99ad-18cd2bb53b41.png)

- 4 wire measurment
	
![image](https://user-images.githubusercontent.com/120498080/214107656-ef09a23c-4ad8-4376-9e20-49d689da36dd.png)
#### Obsevation 
- By using triax cable we found that resistance increases and accuracy decreases.
	
## <h1 id="header-3_4">Measuring the values of Ceramic Capacitor and Electrolytic Capacitor using LCR meter</h1>
- We measured the value of Ceramic Capacitor of 100nF and Electrolytic Capacitor of 10uF using LCR meter and we found that it is varrying with respect to frequency.

#### Table 
![image](https://user-images.githubusercontent.com/120498080/214087418-829ade53-94a3-4ecf-a530-abc91ef531b1.png)
#### Graph
![image](https://user-images.githubusercontent.com/120498080/214244643-bcd4944e-ac54-4d4b-80ce-8e34c3519f1b.png)

## <h1 id="header-3_5">Solving Errors of week1</h1>
- We program SMU using USB cable in Keithley Test Script Builder.
	
![Screenshot (2202)](https://user-images.githubusercontent.com/120498080/214111557-2773fd3a-b701-4854-b051-b1027aae91c1.png)
#### Output Graph
![image](https://user-images.githubusercontent.com/120498080/214111775-1ac28edd-09b0-46e7-9fd6-4ead60d1173e.png)

# Week 4: MOSFET Characterisation
---
In this week we tried to characterise Power mosfet.
	
## Required component:
	
1. Keithley 2636B SMU
2. Triax Cables
3. Power Mosfets (IRF 640 N, IRF 630 N)
4. Breadboard and connectors
	
## IRF640N
	
![image](https://user-images.githubusercontent.com/120498080/215676283-25939412-2494-4709-a966-4552c28c537e.png)
        
The circuit of the power mosfet is shown below. As we can see these MOSFETs have body diodes. Body diode of the MOSFET provides us with a path for inductive load current to by-pass the MOSFET during its “OFF” state, Which is an important feature used in many applications such as synchronous rectification (AC-DC and DC-DC) and motor control (full-bridge & half-bridge). Body diode conduction occurs during the ‘dead-time’ between one MOSFET switching off and the second MOSFET turning on. Although dead-time is typically brief (approximately 80 to 100 nanoseconds) the losses associated with this part of the switching cycle can be significant. There are energy loss mechanisms associated with the body-diode conduction phase.
	
![image](https://user-images.githubusercontent.com/120498080/215676491-adcb9325-a928-401f-ac49-b41bf9cd3152.png)

- [IRF640N Data Sheet](https://drive.google.com/file/d/15YuPCNSOz5lKfFQQqb9ehjZzHD9DQ96F/view?usp=sharing)

## MOS I-V Characterstics 
### (V <sub> DS </sub> vs I <sub> D </sub>)

-  We used kickstart software to plot the I-V Characterstics of Power Mosfet.

The setting which we kept in the kickstart software.
![image](https://user-images.githubusercontent.com/120498080/215683668-3d26211c-5187-4c01-af50-ee61b4feec10.png)

- Setting for DRAIN Terminal:
![image](https://user-images.githubusercontent.com/120498080/215716547-4445a0a9-6ab3-4942-a53e-d2c1df588156.png)

- Settings for GATE terminal: 
![image](https://user-images.githubusercontent.com/120498080/215683801-744bc0fd-4cab-4421-9a4b-11304eb7c95e.png)

- As per the datasheet the gate threshold voltage is: VGS(th) Gate Threshold Voltage 2.0 (Minimum)  4.0 V (Maximum) For,  VDS = VGS, ID = 250µA
- Using kickstart software we got the following plots for IRF 640N MOSFET. Using step size of two we got the following plots:

![image](https://user-images.githubusercontent.com/120498080/215682249-103eb7fb-6c6c-4098-afe3-01fee00dc0d4.png)
	
#### Inference from the above plots:
1. We observe that for 3 V at gate, we do not have any significant amount of current. Hence it can be inferred that the threshold value is greater than 3.
2. For gate voltage of 4 V we get significant amount of current. Hence, it can be inferred that threshold voltage is approximately between 3 to 4 V.

- Now we tweaked the gate voltage and the following plot was observed.
![image](https://user-images.githubusercontent.com/120498080/215682411-bcab2bd1-dc63-4bf7-ba59-1841a3b4a24f.png)
	
#### Inference from the above plots:
1. So, we tried to plot Vgs vs Id curve but we weren’t getting the expected plots. Hence, we need to figure this out.
2. We also observe that for more than 5 V (approximately 4.6 V) and we observed that current was significantly high.


## ERROR:
	
- While sweeping V<sub> GS </sub> vs I<sub> D </sub> we faced following error i.e., TSP link cable are required for pulse mode operation.
	
![image](https://user-images.githubusercontent.com/120498080/215686506-87769fc9-f906-450e-97af-b42cfbb41b6c.png)	

# Week 5: MOSFET Characterisation
---
- This week we characterise 2N7000 N - Channel Enhancement type MOSFET.
- This MOSFET is the second generation of STMicroelectronics unique “Single Feature Size” strip-based process. The resulting transistor shows extremely high packing density for low on-resistance, rugged avalanche characteristics and less critical alignment steps therefore a remarkable manufacturing reproducibility.

## Required component:
	
1. Device Analyzer B1500
2. Triax Cables
3. N - Channel Enhancement MOSFET(2N7000).
4. Breadboard and connectors.

## Device Analyzer B1500
The Keysight B1500A semiconductor parameter analyzer is an all-in-one device characterization analyzer supporting IV, CV, pulse/dynamic IV and more. The mainframe and plug-in modules enable the characterization of most electronic devices, as well as materials, semiconductors, and active/passive components.

 It provides a wide range of measurement capabilities to cover the electrical characterization and evaluation of devices, materials, semiconductors, active/passive components, or virtually any other type of electronic device with uncompromised measurement reliability and efficiency. The B1500A modular architecture gives you the flexibility to upgrade when needed.

![B1500_FL_TRANS_SHAD_2016April13](https://user-images.githubusercontent.com/120498080/217153264-21332b77-ab89-4d45-afc1-3dc17cd4f7cc.png)

	
## 2N7000 MOSFET
	
2N7000 is a small signal N-channel MOSFET. MOSFET's are power electronic switches just like transistors, but with a higher current and voltage rating. The 2N7000 MOSFET can be used to switch loads which operates on less than 60V (VDS) and 200mA (ID).2N7000 is a small signal N-channel MOSFET. MOSFET's are power electronic switches just like transistors, but with a higher current and voltage rating. The 2N7000 MOSFET can be used to switch loads which operates on less than 60V (VDS) and 200mA (ID).

This mosfet has a threshold voltage of 3V, hence if you looking for a small mosfet to switch a load then this IC could suit your purpose.
	
![Pinout-of-2N7000-N-channel-Enhancement-MOSFET](https://user-images.githubusercontent.com/120498080/217152678-2bff1462-b71f-4959-a62a-e7e7c0214844.png)
	
- [2N7000 MOSFET Data Sheet](https://www.st.com/resource/en/datasheet/cd00005134.pdf)
	

## MOSFET Id-Vg Characterstics 

![id vs vg](https://user-images.githubusercontent.com/120498080/216812596-aa9cd1a8-0ae8-4d46-b527-19a834e7e4e4.jpg)

- By the above plot we can conclude that the threshold voltage **V<sub>th</sub> = 1.8V.**
	
According to the Datasheet.

![image](https://user-images.githubusercontent.com/120498080/217154007-9f4c297b-f015-4b44-bfbd-b15ab70476dd.png)

	
## MOSFET Id-Vd Characterstics 

- We have plotted drain current while sweeping the drain voltage from 0 to 10 V for different values of Vgs. From the plot we can infer that our plot is mainly restricted by the current limitations of the the device analyser i.e., 100 mA. 
	
![2N7000 Id vs Vd](https://user-images.githubusercontent.com/120498080/216812381-eab6cfcb-825f-4fbf-871d-59233828a28e.png)


## MOSFET log(Id) - Vg Characterstics 

![log idvsvg](https://user-images.githubusercontent.com/120498080/216812650-3f5999d4-4e1d-4e11-96ca-14dcb6b78d00.jpg)

- From the above plot we can calculate the I <sub>off</sub> (off current) and subthreshold swing.

**I <sub>off</sub> (off current) = 10 pA**

**Subthreshold Swing = 166 mV/dec**

## MOSFET gm - Vg Characterstics 
	
Again we got restricted by the current limit of the Device Analyzer.

![gmvsvg](https://user-images.githubusercontent.com/120498080/216812705-583b637a-a43b-40eb-bc8e-52acbeb20483.jpg)

## MOSFET Hf - CV Characterstics 
	
- Theoretically

At high frequency our Gate voltage varries rapidly, in response the this the inversion charge does not respond. This is due to the fact that minority charge carrier require some time for being generated in the bluk. Hence there is no generation and recombination at high frequency in inversion region.  

![hfcv](https://user-images.githubusercontent.com/120498080/216813202-5515ffb2-71c7-47fa-a907-e9a676b95e7f.jpg)

### Inference from the above plots:

- We don't get the desired CV plot as per theory at high frequency. This can be due to the fact that drain and source are large reservior of minority carrier and during high frequency switching of the GATE voltage these reservior assist in the formation of genration and recombination (in the sense that these provide the MOSFET with minority carrier which according to theory are deficient in the device), hence we get the above curve. 
	
- The above curve is shifted from the orgin this can be due to the presence of fixed charges present in Si - SiO<sub>2</sub> interface  or the work function difference between metal and semiconductor.
	
- We can also calculate the value of Cox, Cdmin, Wdmax, etc. (if the material properties and dimensions are given).




# Week 6: MOSFET Characterisation
---
- This week we characterise N- Channel Enhancement type MOSFET in CD4007 Dual Complementary Pair Plus Inverter which has low current limitations.

## Required component:
	
1. Device Analyzer B1500
2. Triax Cables
3. CD4007 Dual Complementary Pair Plus Inverter
4. Breadboard and connectors.


## CD4007 Dual Complementary Pair Plus Inverter

![download](https://user-images.githubusercontent.com/120498080/218643129-2cd1afae-4f02-4716-b595-8fa9a5c8a75e.jpg)
	
CD4007UB types are comprised of three n-channel and three p-channel enhancement type MOS transistors. The transistor elements are accessible through the package terminals to provide a convenient means for constructing the various typical circuits as shown below

![image](https://user-images.githubusercontent.com/120498080/218642785-271a17ff-ba61-4d90-9cdc-8955196ef12f.png)

This mosfet has approximate values for the threshold voltage of the NMOS in the three cases, which are: 1.6 V, 2.6 V, 3.3 V for V DD = 5 V, 10 V, 15 V respectively. 
	
- [CD4007 Dual Complementary Pair Plus Inverter Data Sheet](https://datasheet.octopart.com/CD4007UBE-Harris-datasheet-115824.pdf)
	

## nMOS Id-Vg Characterstics 
![idvg vd](https://user-images.githubusercontent.com/120498080/218643433-eaba8762-7d3a-4d4a-99c2-f52e5996beba.jpg)

- By the above plot we can conclude that the threshold voltage **V<sub>th</sub> = 1.2V.**
	
### nMOS Id-Vg Characterstics from -5 to +5V
	
![id vg -5to5](https://user-images.githubusercontent.com/120498080/218644299-37fc2f29-bfea-421a-a908-5c76b2b649dd.jpg)

## nMOS log(Id)-Vg Characterstics 

![logid vg vd](https://user-images.githubusercontent.com/120498080/218645437-918f0089-abe8-41c9-8be8-868895e6a5e6.jpg)

- From the above plot we can calculate the I <sub>off</sub> (off current) and subthreshold swing.

**I <sub>off</sub> (off current) = 8 pA**

**Subthreshold Swing = 151 mV/dec**

## nMOS gm-Vg Characterstics 
	
![gm vg vd](https://user-images.githubusercontent.com/120498080/218646138-d08a4f92-be5e-4580-a111-51c2200db020.jpg)

## Calculation of threshold voltage
![vt cal](https://user-images.githubusercontent.com/120498080/218646285-ef5e11df-1975-4fae-8353-e3e69ae88dec.jpg)

- We got a theshold voltage of 0.9V

![id vg 100mV](https://user-images.githubusercontent.com/120498080/218691046-45ad7a76-8f4b-4e0e-8329-eac209704ab4.jpg)
- We took Vds=100mV(linear region) and we got a Vth=1.17V

![id vg 2V](https://user-images.githubusercontent.com/120498080/218691079-eae1ae55-e758-435f-8c6c-1bb75f181e4f.jpg)
- We took Vds=2V(saturation region) and we got a Vth=2.05V

## nMOS Id-Vg for varing Vb Characterstics 	
	
- We plotted Id - Vg by changing the value of body voltage.
![IDVG-VB](https://user-images.githubusercontent.com/120498080/218660315-b265c5f7-9334-430f-905a-f344e580b4ff.jpg)
	
## nMOS Id-Vd Characterstics 

- We have plotted drain current while sweeping the drain voltage from 0 to 5 V for different values of Vgs. 

![id vd multiple](https://user-images.githubusercontent.com/120498080/218687902-72b12352-a56b-421c-9e02-2d6ed516cc53.jpg)

## nMOS Hf-CV Characterstics 
	
![cv lcr cable](https://user-images.githubusercontent.com/120498080/218648905-736fb0d2-f7a6-4d8a-8db8-8cb1ba2e673f.jpg)
 
- We tried to plot CV curve but we where unsuccessful and we where getting plot from -2 to +5V insted of -5 to +5V. Also we where fetting negative value of capacitance.
- So next week we will try to figure it out.



# Week 7: MOSFET Characterisation
---
- This week we characterise P- Channel Enhancement type MOSFET in CD4007 Dual Complementary Pair Plus Inverter which has low current limitations.

## Required component:
	
1. Device Analyzer B1500
2. Triax Cables
3. CD4007 Dual Complementary Pair Plus Inverter
4. Breadboard and connectors.


## CD4007 Dual Complementary Pair Plus Inverter

![download](https://user-images.githubusercontent.com/120498080/218643129-2cd1afae-4f02-4716-b595-8fa9a5c8a75e.jpg)
	
CD4007UB types are comprised of three n-channel and three p-channel enhancement type MOS transistors. The transistor elements are accessible through the package terminals to provide a convenient means for constructing the various typical circuits as shown below

![image](https://user-images.githubusercontent.com/120498080/218642785-271a17ff-ba61-4d90-9cdc-8955196ef12f.png)

This mosfet has approximate values for the threshold voltage of the NMOS in the three cases, which are: 1.6 V, 2.6 V, 3.3 V for V DD = 5 V, 10 V, 15 V respectively. 
	
- [CD4007 Dual Complementary Pair Plus Inverter Data Sheet](https://datasheet.octopart.com/CD4007UBE-Harris-datasheet-115824.pdf)
	
## Circuit

![IMG_20230219_152156](https://user-images.githubusercontent.com/120498080/220278058-dd80fe56-ed2f-4c08-92b1-22aaea718754.jpg)


## pMOS Id-Vg Characterstics 
![pmos id-vg](https://user-images.githubusercontent.com/120498080/220154041-adf368c7-9c2f-44c1-89b7-52bdcd714583.png)


- By the above plot we can conclude that the threshold voltage **|V<sub>th</sub>| = 1.8V.**
	
## pMOS log(Id)-Vg Characterstics 

![log id-vg](https://user-images.githubusercontent.com/120498080/220154336-cff6f3d1-1c3c-462d-9c95-cffe67821d52.png)


- From the above plot we can calculate the I <sub>off</sub> (off current) and subthreshold swing.

**I <sub>off</sub> (off current) = 5 pA**

**|Subthreshold Swing| = 83.34 mV/dec**

# Week 8: MOSFET Characterisation and LDR
---
## In Id-Vg why we got high current at negative voltage of CD4007
![Id-Vg -ve NMOS](https://user-images.githubusercontent.com/120498080/221778236-9e99abae-b520-4358-9c81-c4718bc36931.jpg)

## Gate Current
![photo_2023-02-28_12-19-57](https://user-images.githubusercontent.com/120498080/221778978-6404705b-b100-4ebf-a463-c52193c590c6.jpg)

## Designing Inverter of CD4007 IC
- When we give 0 to 10V

![photo_2023-02-28_12-19-57 (2)](https://user-images.githubusercontent.com/120498080/221779761-ba3c303c-f7a5-4e39-9865-4c7510f6a897.jpg)
- When we give -5V to 5V

![photo_2023-02-28_12-19-57 (7)](https://user-images.githubusercontent.com/120498080/221779979-d7111ba6-a735-45f4-a320-d83ca23e0ea1.jpg)

## Light Dependent Resistor 
LDR (Light Dependent Resistor) as the name states is a special type of resistor that works on the photoconductivity principle means that resistance changes according to the intensity of light. Its resistance decreases with an increase in the intensity of light. It is often used as a light sensor, light meter, Automatic street light, and in areas where we need to have light sensitivity. It is also called a Light Sensor.

![image](https://user-images.githubusercontent.com/120498080/224896560-44818bb4-5268-48d0-ac3d-ec8fb69bb66e.png)

LDR are usually available in 5mm, 8mm, 12mm, and 25mm dimensions.

![image](https://user-images.githubusercontent.com/120498080/224897517-07ec291b-11ee-45ec-a40b-5c46acba3d91.png)

### Graph of 5mm LDR

### Graph of 12mm LDR

# Week 9: MOSFET Characterisation
---
## STAKING EFFECT	
Transistor stacking is a technique used in active mode for leakage power reduction. The leakage current decreases when two or more series transistors are turned off, which is known as Stack effect or Self-Reverse bias effect.
	
### Leakage Current in one NMOS
![1 nmos](https://user-images.githubusercontent.com/120498080/224898958-67ef3e49-8f30-4d1a-8c3a-79c09dc1560e.jpg)
	
### Leakage Current in two NMOS in series
![2 nmos](https://user-images.githubusercontent.com/120498080/224901301-396754e2-3737-4edd-9ab8-df5fd5be73e1.jpg)


	
	



# <h1 id="header-r">References</h1>
- [**SMU** - Keithley Source Meter 2636B Manual](https://www.manualslib.com/products/Keithley-Sourcemeter-2636b-8711107.html)
- [RMT2054 Oscilloscope Manual](https://scdn.rohde-schwarz.com/ur/pws/dl_downloads/dl_common_library/dl_manuals/gb_1/r/rtm_1/rtm1000_2000/rtm1000_1/RTM_UserManual_en.pdf)
- [Wayne Kerr LCR meter 4300 Series Manual](https://www.waynekerrtest.com/datasheet/instruments/wk4300.pdf)
- [Device Analyzer B1500 Manual](https://www.keysight.com/us/en/assets/9018-01850/user-manuals/9018-01850.pdf)
	
	
# <h1 id="header-a">Acknowledgement</h1>
- [Dr. Naresh Kumar Emani](https://www.iith.ac.in/ee/naresh/)

