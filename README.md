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
        <li><a href="#header-2_2">Experiement 2.1: Measurement of Capacitor value & Cutoff frequency from RC Filters</a></li>
      </ul>
	<ul>
        <li><a href="#header-2_3">Experiement 2.2: Measurement of Inductor value & Cutoff frequency from RL Filters</a></li>
      </ul>
	<ul>
        <li><a href="#header-2_3">Experiement 2.3: Measurement of Resonance & Cutoff frequency from RLC Filters</a></li>
      </ul>
</div>	
	
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

# <h1 id="header-1">1. Familiarization with Instrumentation</h1> 
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

1.Sourcing Voltage (Source = 50 mv), Limit to Current = 200 mA
![image](https://user-images.githubusercontent.com/120498080/211482799-d4c8e27f-1887-404a-9fd0-16ccfba93c29.png)

2. Sourcing Current (Source = 200 mA), Limit to Voltage = 50 mV
![image](https://user-images.githubusercontent.com/120498080/211482972-cffd614c-41ea-4548-93b6-f76243942d19.png)

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
1.We tried to remotely control the SMU using TSB software and faced issues in auto run.

![image](https://user-images.githubusercontent.com/120498080/211484356-38fd3c98-b60e-4bbb-81bc-8bb161a292a2.png)
2.Faced error in measuring resistance using TRIAX cable to measure resistance.


### Experiment when we use triax and BNC coverter.

# <h1 id="header-2">Week 2. Familiarization with Instrumentation</h1>
## <h1 id="header-2_1">Familiarization to Oscilloscope</h1> 
### Oscilloscope
An oscilloscope is a test & measurement instrument that rapidly measures voltage over time. It records the voltage across certain points in a circuit and displays voltage (Y-axis) as a function of time (X-axis) on a screen. It is essentially a very fast voltmeter with the capability of data-logging and plotting.
- We are using RMT2054 Oscilloscope
![download](https://user-images.githubusercontent.com/120498080/212805807-d82d6927-f737-4bb3-a4c9-ef3883904824.jpeg)


## <h1 id="header-2_2">Experiement 2.1: Measurement of Capacitor value & Cutoff frequency from RC Filters</h1> 
	
**Equipments Required:**
- Resistance and Capacitor (Resistance =  1kohms with precision of ±0.1 ohm and Capacitor of 0.2uFarad)
- Multimeter
- BNC(Bayonet Nut Coupling) Cables
- RMT2054 Oscilloscope
- 33600A Waveform Generator

**Procedure:**
	
**Step 1:** Hand Calculation and selected components
   - Selected value of capacitance = 200 nF
   - Selected value of resistance = 1 Kohm
   - Cut- off frequency = 1/2πRC 
   - Calculated Cut-off frequency = 795 Hz
	
**Step 2:** Establishing Connections
	
![rc-low-pass-filter](https://user-images.githubusercontent.com/120498080/212807171-e3561edb-00f9-4a5a-b410-7ef7f0c6dc0e.jpg)
- We connect the R and C component in series and provide input between R and C and take output from C. 
- Applied peak to peak Voltage (Vpp = 1 V)
	
**Step 3:** Calculating the value of Capacitance using the value phase shift in input and output.
 - As we know for RC circuit, 
 - tan (Φ) = 1/ωRC
	
	C = 1/( ωRtan (Φ) )
	
- The calculated values of capacitance are as follows:
![image](https://user-images.githubusercontent.com/120498080/212817564-990f61b8-3fae-4c72-bed7-ed23bbdc2f68.png)
 
### Output of our RC low pass filter:
- At 500 Hz. (yellow – output, green – input)
![image](https://user-images.githubusercontent.com/120498080/212817642-0f1f11d4-3101-471a-9c80-467486ad63cb.png)
![image](https://user-images.githubusercontent.com/120498080/212817664-ddfa4e46-1673-4f26-a2f8-27ddd97bfe56.png)
![image](https://user-images.githubusercontent.com/120498080/212817696-142f70d9-a3a4-46e9-a408-9dd9c28b7199.png)
- Result: The cut-off frequency of RC filter is 2kHz
	
### Output at cut-off frequency
![image](https://user-images.githubusercontent.com/120498080/212818022-63b1c7b0-2792-4870-910f-bd788328b445.png)
![image](https://user-images.githubusercontent.com/120498080/212818055-a746f4ff-4e74-43a7-9243-3dba9933d31f.png)

	
	
	
	


	
	

	

## <h1 id="header-2_3">Experiement 2.2: Measurement of Inductor value & Cutoff frequency from RL Filters</h1>

**Equipments Required:**
- Resistance and Inductor (Resistance =  1kohms with precision of ±0.1 ohm and Inductor of 1mHenry)
- Multimeter
- BNC(Bayonet Nut Coupling) Cables
- RMT2054 Oscilloscope
- 33600A Waveform Generator

**Procedure:**

![rl](https://user-images.githubusercontent.com/120498080/212808528-3d8a6bc3-6437-463b-b2f5-a5e74430690d.PNG)
	
## <h1 id="header-2_4">Experiement 2.3: Measurement of Resonance & Cutoff frequency from RLC Filters</h1>
**Equipments Required:**
- Resistance , Capacitor and Inductor (Resistance =  1kohms with precision of ±0.1 ohm , Capacitor of 0.2uFarad and Inductor of 1mHenry with precision of ±0.1 ohm )
- Multimeter
- BNC(Bayonet Nut Coupling) Cables
- RMT2054 Oscilloscope
- 33600A Waveform Generator

**Procedure:**

**Step 1:** Hand Calculation and selected components
   - Selected value of capacitance = 200 nF
   - Selected value of resistance = 1 Kohm
   - Selected value of inductor = 1 mHenry
   - Lower Cut- off frequency = 1/2πRC
   - Higher Cut- off frequency = R/2πL
   - Resonance frequency - 1/2π√LC
	
	
	
   - Calculated Cut-off frequency = 795 Hz
	
**Step 2:** Establishing Connections
	
![rc-low-pass-filter](https://user-images.githubusercontent.com/120498080/212807171-e3561edb-00f9-4a5a-b410-7ef7f0c6dc0e.jpg)
- We connect the R and C component in series and provide input between R and C and take output from C. 
- Applied peak to peak Voltage (Vpp = 1 V)
	
**Step 3:** Calculating the value of Capacitance using the value phase shift in input and output.
 - As we know for RC circuit, 
 - tan (Φ) = 1/ωRC
	
	C = 1/( ωRtan (Φ) )
	
![rlc](https://user-images.githubusercontent.com/120498080/212808368-9d2b9475-ffd2-4ed2-b21e-55e88872f083.PNG)

	


	
### ERROR FACED:
- In function generator when we give 1Vpp then in oscilloscope it was giving 1.19Vpp sine wave - but this was fixed when we changed the BNC converter on Oscilloscope.
 
	
# <h1 id="header-r">References</h1>
- [**SMU** - Keithley SourceMeter 2636B Manuals](https://www.manualslib.com/products/Keithley-Sourcemeter-2636b-8711107.html)
- 
# <h1 id="header-a">Acknowledgement</h1>
- [Dr. Naresh Kumar Emani](https://www.iith.ac.in/ee/naresh/)
