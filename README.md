# Device-Characterization-Lab

# Table of Contents
<div class="toc">
  <ul>
    <li><a href="#header-1">1. Familiarization with Instrumentation</a></li>
	<ul>
        <li><a href="#header-1_1">Familiarization the functions of SMU (Source Measuring Unit)</a></li>
      </ul>
      <ul>
        <li><a href="#header-1_2">Experiement1: Measurement of accuracy in low resistance measurement</a></li>
      </ul>
      <ul>
        <li><a href="#header-1_3">Familiarization to Oscilloscope</a></li>
      </ul>
	  </ul>
	  
	
</div>
<div class="toc">
  <ul>
    <li><a href="#header-6">References</a></li>
  </ul>
</div>

<div class="toc">
  <ul>
    <li><a href="#header-7">Acknowledgement</a></li>
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

### BNC Cable vs Triax Cable vs SMA Cable 
| BNC Cable | Triax Cable | SMA Cable |
|:----------:|:-------------------:|:---------------------:|
| The BNC connector (initialism of "Bayonet Neill–Concelman") is a miniature quick connect/disconnect radio frequency connector used for coaxial cable. | Triaxial cable, often referred to as triax for short, is a type of electrical cable similar to coaxial cable, but with the addition of an extra layer of insulation and a second conducting sheath. It provides greater bandwidth and rejection of interference than coax, but is more expensive. | The abbreviation SMA stands for “Sub-Miniature Version A”. In order to maintain the transmission speed of coaxial cables, both versions of the corresponding connectors have a coaxial design. They therefore have good electrical shielding and low electromagnetic |
|![download (89)](https://user-images.githubusercontent.com/120498080/210628269-9c35f866-2aaf-4dc9-9df3-059afdc9676e.jpeg)|![Belden-Triax-Cables-Family-Fanout](https://user-images.githubusercontent.com/120498080/210628528-e8cf3cb5-8a50-48e1-bc87-28370a057a6b.jpg)|![download (90)](https://user-images.githubusercontent.com/120498080/210628760-f5d77605-e7d7-4be8-bcf5-56107b89d6d6.jpeg)
|

<h1 id="header-1_2">Experiement1: Measurement of accuracy in low resistance measurement</h1> 
**Equipments Required:**

1.	Low Resistance (selected resistance = 0 ohms with precision of ±0.1 ohm)

2.	Multimeter

3.	Banana Cables

4.	SMU (Keithley 2450)

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
Step 4: Using 4probe method and measure the resistance value using Keithley 2450 
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





### Experiment when we use triax and BNC coverter in series.





### Why sometimes we get differnet output graphs even if we use same instrument, same cable and same device.
Reason behind this is **Charge trapping** - Charge trapping refers to the localization of the electron or hole at lattice defects within the crystal structure or at unsaturated bonds on the nanocrystal surface atoms. The charge can become stabilized in these sites, called trapping states, and, therefore, trapping reduces charge mobility in nanocrystal arrays.

//### Measurment vs Accuracy
//Accuracy refers to how close a measurement is to the true or accepted value. Precision refers to how close measurements of the same item are to each other. Precision //is independent of accuracy.



### How to measure low resistance 
To measure the low value resistance such as 1 milli-ohm the resistance of interconnects will create the problem.
For the measurement of low resistances, the following methods are used :−

- Ammeter-Voltmeter Method
- Potentiometer Method
- Kelvin Double Bridge Method

[Refrence](https://www.tutorialspoint.com/how-to-measure-low-resistances-resistance-measurement-methods)





## <h1 id="header-1_3">Familiarization to Oscilloscope</h1> 
### Oscilloscope






# <h1 id="header-6">References</h1>
- [**SMU** - Keithley SourceMeter 2636B Manuals](https://www.manualslib.com/products/Keithley-Sourcemeter-2636b-8711107.html)
- 
# <h1 id="header-7">Acknowledgement</h1>
- [](https://www.iith.ac.in/ee/naresh/)
