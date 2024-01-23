# DC_Supply_5.5kW Hardware 
This is the project page for an open source 5.5kW 12-150VDC Supply (250A Max).    

## Design Architechture

<img src="https://github.com/offbyfour/DC_Supply_5p5kW/assets/124545095/994654e8-f2a7-4c3c-b209-a4668d5c7fc9" width="525" height="225" />

The architecture of this design consists of 5 main blocks with the most complex being the converters. Below is a breakdown of the functions and the features of each.

### Input Interfaces
The input interface is basically how the supply gets connected to the wall. Since there are multiple plugs that can be used, the best solution seems to be something like the Miller MVP System. This system consists of a cable with a general purpose connector that can be connected to any specific connector the user needs.

Miller video for reference:https://www.youtube.com/watch?v=PGal35EDwXY

#### Features 
- 2m(6.5ft) 30A Cable
- GFCI Protection
- Interchangeable NEMA Plugs
  - 14-30
  - 6-30
  - 5-15
  - 5-20

### AC/DC Conversion

<img src="https://github.com/offbyfour/DC_Supply_5p5kW/assets/124545095/d830a15b-c6bc-48bc-910b-730c702645bf" width="425" height="225" />

The AC/DC conversion consists of an off the shelf converter used in parallel. The supply is programmable for 42VDC-58VDC operation through the PMBus interface. Current-controlled operation is also an option.

#### AC Input Features 
- Input Voltage: 85VAC-300VAC
- Input Current (max): 24A
- Line Frequency: 45-65Hz
- Power Factor (@50-100% load) : >99%
  
#### DC Output Features 
- Output Voltage: 42VDC-58VDC
- Output Current (max): 130A
- Output Power (max): 5,531W
- Target Efficiency (@>20% load): >97%

#### General Features 
- Operating Temperature: -40C - 45C
- Storage Temperature: -40C - 85C
  
### DC/DC Conversion
<img src="https://github.com/offbyfour/DC_Supply_5p5kW/assets/124545095/896f9e09-c65d-4644-9b35-155087ce87f8" width="525" height="225" />

The DC/DC conversion will consist of a cascaded Buck-Boost converter. This configuration was chosen due to its high conversion efficiency and flexibility.

#### DC Input Features 
- Input Voltage: 42VDC-58VDC
- Input Current (max): 130A

#### DC Output Features 
- Output Voltage: 12VDC-150VDC
- Output Current (max): 250A
- Output Power (max): 5,420W
- Target Efficiency (@>20% load): >98%

#### General Features 
- Operating Temperature: -40C - 45C
- Storage Temperature: -40C - 85C

### Controller
The controller will contain the interface which the user can use to set all the different modes and settings.

#### Features 
- Soft-Start 
- Constant Voltage
- Constant Current
  - Average current mode
  - Peak current mode
- Constant Resistance
- Constant Power
- Second Stage Passthrough: Operation mode which eliminates EMI and switching losses, and maximizes efficiency (up to 99.9%) through the second stage converter. Passthrough operation passes the input directly to the output when the input voltage is within the output voltage range of the first stage.

### Output Interfaces 

The output interface is a floating positive and negative terminal. Since the output voltage can reach 150V, they need to be adequately protected. Since it will also be dealing with currents of around 250A, the connector will need to be low resistance. As a nice to have, it would be good if the connector would also support a gas passthrough.

#### Features 
- 2x 4m(13ft) 285A Cable (#1 AWG) (PWR + GND)
- 4x 50mm Dinse Style Connector with air passthrough
- 4x 50mm Dinse Style Receptacle with air passthrough

### Sources

1. Pass Through Operation: https://www.analog.com/en/design-notes/4-switch-buck-boost-controller-with-pass-thru-capability-eliminates-switching-noise.html
2. Constant Current and Voltage:https://www.rohde-schwarz.com/us/products/test-and-measurement/essentials-test-equipment/dc-power-supplies/understanding-constant-voltage-current-_256008.html
3. Dinse-style connector: https://dinse-us.com/wp-content/uploads/sites/2/2014/07/DINSE_Plugs_Sockets_US.pdf

