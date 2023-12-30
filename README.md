# DC_Supply_5.5kW
This is the project page for an open source 5.5kW 12-150VDC Supply (250A Max). The goal of this page is to provide complete instructions, component lists, HW and SW files to build this project from start to finish.   


## Target Output Range

<img src="https://github.com/offbyfour/DC_Supply_5p5kW/assets/124545095/38fa2b41-4610-4b81-bc3a-e3d09f37e809" width="325" height="225" />

The target output of this supply is 5.5kW or 250A, whichever is hit first for a range of 12VDC to 150VDC.

## Target Input Range

<img src="https://github.com/offbyfour/DC_Supply_5p5kW/assets/124545095/8a916794-4754-4f9d-a5e0-06564cb87cd8" width="325" height="225" />

The target input of this supply has the same requirements as the telecom rectifiers used in the first stage converter. Input can be anywhere from 85VAC to 300VAC @ 45-65Hz. The input should be robust enough to support being powered from a dirty power source like a generator.

## Target Use Cases

<img src="https://github.com/offbyfour/DC_Supply_5p5kW/assets/124545095/fe7318e0-02b1-4852-ae78-f406d180a809" width="125" height="125" /> <img src="https://github.com/offbyfour/DC_Supply_5p5kW/assets/124545095/b6b53d70-a962-4253-9a7c-2ca6dcd8624b" width="125" height="125" />

The primary goal of this supply is to maximize the DC power available from the 240VAC@30A outlet found in most homes. From searching online, the most power that any device can safely pull from one of these circuits is 80% or 24A. At 240VAC, this means the maximum power that can be pulled from the wall is 5,760W. Because of this, the target efficiency of this design will be 95% resulting in 5,472W of available output power.

The secondary goal of this design is to work with 120VAC@15A circuits at a reduced power level. Using the same 80% safety rule, leaves 12A available from the wall or 1,440W. The target efficiency of this design at this lower power level will also be 95% resulting in 1,368W of output power. 


## AC/DC Conversion (First Stage Conversion)

<img src="https://github.com/offbyfour/DC_Supply_5p5kW/assets/124545095/3a0c926a-70ba-442c-9201-c35aaedb96d9" width="225" height="125" /> 

To start out, the first stage of this design will use an off the shelf converter. The R48-3000e3 supplies have a few characteristics that  make it nice for this application:

1. Cheap and easy to find  (about $100-$200 but even cheaper in some places)
2. Programmable output voltage (42VDC-58VDC)
3. Hot-pluggable and Stackable (for additional power support)
4. Wide input voltage range (85 300VAC) for better flexibility and so that it can work with dirty supplies like generators.

But the main reason these supplies would be good to use is because they wont require significant exposure to high voltages which make them a little easier to DIY. Although there could be the drawback that this is probably not the most efficient way to Implement the design.

Two paralleled supplies should be enough to meet the requirements for this design. When supplied with 240VAC, these supplies will output 48VDC @ 124A. However the plan is to operate at ~90% capacity or 114A.

Eventually this stage will also be open source with a target conversion efficiency of 97%.

## DC/DC Conversion Second Stage Conversion

<img src="https://github.com/offbyfour/DC_Supply_5p5kW/assets/124545095/43a9c41e-d027-4d3e-b6df-ee028ca86305" width="225" height="125" /> 

This stage of the design is what will involve most of the work in this project. The target efficiency for this part is around 98%. This is also the part of the design that will need to be able to handle at least 250A.

Due to the wide output range necessary a cascaded buck-boost supply seems the best configuration. Also, because of the high efficiency requirements, GaN fets seem to be the best switch to use.


## Project Status

<img src="https://github.com/offbyfour/DC_Supply_5p5kW/assets/124545095/4eff57e3-ac06-48fe-8114-b59e78c0e51f" width="225" height="125" /> 

Right now this project is in the design stage. If you would like to contribute in any way feel free to make a pull request or email me at zero.offbyfour@gmail.com 


## Sources
1. Telecom Rectifier R48-3000e:https://www.vertiv.com/globalassets/products/critical-power/dc-power-systems/netsure-731-a412/r48-3000e3-datasheet.pdf
2. Common Power Outlets: https://getneocharge.com/a/blog/types-of-electrical-outlets-for-electric-car-chargers
3. DC/DC Design Topologies: https://journals.pan.pl/dlibra/publication/135986/edition/118907/content/international-journal-of-electronics-and-telecommunications-2021-vol-67-no-3-design-analysis-and-comparison-of-si-and-gan-based-dc-dc-wide-input-voltage-rangebuck-boost-converters-br-koszel-mikolaj-grzejszczak-piotr-nowatkiewicz-bartosz-wolski-kornel?language=en

