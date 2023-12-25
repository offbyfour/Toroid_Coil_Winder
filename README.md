# DC_Supply_5.5kW
Open Source 5.5kW 12-150VDC Supply (250A Max)


## Target Output Range

<img src="https://github.com/offbyfour/DC_Supply_5p5kW/assets/124545095/38fa2b41-4610-4b81-bc3a-e3d09f37e809" width="325" height="225" />

As shown in the graph above, the target output of this supply is 5.5kW or 250A, whichever is hit first for a range of 12VDC to 150VDC.

## Target Input Range

<img src="https://github.com/offbyfour/DC_Supply_5p5kW/assets/124545095/8a916794-4754-4f9d-a5e0-06564cb87cd8" width="325" height="225" />

## Target Use Cases

<img src="https://github.com/offbyfour/DC_Supply_5p5kW/assets/124545095/fe7318e0-02b1-4852-ae78-f406d180a809" width="125" height="125" /> <img src="https://github.com/offbyfour/DC_Supply_5p5kW/assets/124545095/b6b53d70-a962-4253-9a7c-2ca6dcd8624b" width="125" height="125" />

The primary goal of this supply is to maximize the power from the 240VAC@30A outlet found in most homes. From searching online, the most power that any device can safely pull from one of these circuits is 80% or 24A. At 240VAC, the most power that can be pulled from the wall is 5,760W. Because of this, the target efficiency of this design will be 95% resulting in 5,472W of output power.

The secondary goal of this design is to work with 120VAC@15A at a reduced power level. Using the same 80% rule, leaves 12A or 1,440W. The target efficiency of this design at this lower power level will also be 95% resulting in 1,368W of output power. 


## AC/DC Conversion (First Stage Conversion)

<img src="https://github.com/offbyfour/DC_Supply_5p5kW/assets/124545095/3a0c926a-70ba-442c-9201-c35aaedb96d9" width="225" height="125" /> 
The R48-3000e3 supplies have a few characteristics that  make it nice for this application:
1. Cheap and easy to find  (about $100-$200 but even cheaper in some places)
2. Programmable output voltage (42VDC-58VDC)
3. Hot-pluggable and Stackable (for additional power support)
4. Wide input voltage range (85 300VAC) for better flexibility and so that it can work with dirty supplies like generators.

But the main reason these supplies would be good to use is because they wont require significant exposure to high voltages which make them a little easier to DIY. Although there could be the drawback that this is probably not the most efficient way to supply the circuit.

Two paralleled supplies should be enough to meet the requirements for this design. When supplied with 240VAC, these supplies will output 48VDC @ 124A. However the plan is to operate at 90% capacity at most.

## DC/DC Conversion Second Stage Conversion


## Sources
1. Telecom Rectifier R48-3000e:https://www.vertiv.com/globalassets/products/critical-power/dc-power-systems/netsure-731-a412/r48-3000e3-datasheet.pdf
2. 


