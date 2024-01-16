# DC_Supply_5.5kW Hardware 
This is the project page for an open source 5.5kW 12-150VDC Supply (250A Max).    

## Design Architechture

<img src="https://github.com/offbyfour/DC_Supply_5p5kW/assets/124545095/448804d7-7648-45e1-bea0-705519238e38" width="525" height="225" />

The architecture of this design consists of 5 main blocks with the most complex being the converters. Below is a breakdown of the functions and the features of each.

### Input Interfaces
The input interface is basically how the supply gets connected to the wall. Since there are multiple plugs that can be used, the best solution seems to be something like the Miller MVP System. This system consists of a cable with a general purpose connector that can be connected to any specific connector the user needs.

#### Features 
- 2m(6.5ft) 30A Cable
- GFCI Protection
- Interchangeable NEMA Plugs
  - 14-30
  - 6-30
  - 5-15
  - 5-20

### AC/DC Conversion

<img src="https://github.com/offbyfour/DC_Supply_5p5kW/assets/124545095/35438aee-e772-4b5f-b2c0-1dc19fe88750" width="525" height="425" />


### Controller

### DC/DC Conversion

### Output Interfaces 

The output interface is a floating positive and negative terminal. Since the output voltage can reach 150V, they need to be adequately protected. Since it will also be dealing with currents of around 250A, the connector will need to be low resistance. As a nice to have, it would be good if the connector would also support a gas passthrough.

#### Features 
- 2x 4m(13ft) 285A Cable (#1 AWG) (PWR + GND)
- 4x 50mm Dinse Style Connector with air passthrough
- 4x 50mm Dinse Style Receptacle with air passthrough



