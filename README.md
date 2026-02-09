# micromouse

This repository consists of my PCB design of the micromouse robot. 
You can see the schematic and the layout pdf for quick glance.

To download the kicad files navigate to schematic-layout-files directory.

The micromouse is one of the oldest robotics race.
The goal is simple: get to the end of the maze as fast as possible.

This is actually my first prototype PCB for the robot, At the time of writing- I have soldered the components, including the buck converter SMPS circuit. I am using a 12V battery to power the robot. The buck converter circuit did not work, one of the possible cause- according to my limited knowledge right now, could be the use of 470uF aluminum capacitor as opposed to the recommended 680-2000uF aluminum capacitor.

The datasheet had recommened that the output capacitor can be between 100uF to 470uF if it is a tantalum capacitor.
If an aluminium capacitor were to be chosen, it had to be in between 680uF-2000uF.
According to the datasheet, 
```
Tantalum capacitors can have a very low ESR, and must be carefully evaluated if it is the only output capacitor
```
And the ESR matters, because 

```
Output Ripple Voltage = (∆IIND) (ESR of COUT) 
```
Lesser the ESR of the output capacitor, lesser would be output ripple voltage, stabler would be the output

Components used in the micromouse are-

| STM32F407VGT6                                                                               | Main microcontroller                      |   |   |   |
|---------------------------------------------------------------------------------------------|-------------------------------------------|---|---|
| N20 600 RPM Micro-Metal gear motor                                                          | Motor for driving the robot               |   |   |   
| LM2576 5V Output SMPS Switcher IC- HTC   Korea                                              | Stepping down voltage from 12V to 5V      |   |   |   
| AMS 1117 3.3V LDO                                                                           | Stepping down voltage from 12V to 5V      |   |   |   
| HM-BT4502 bluetooth module                                                                  | For wirelessly receiving data from the uC |   |   |   
| IR   Emitter/Receiver pair(could be replaced with more accurate and cheaper mmWave radar)   | For sensing the distance from the walls   |   |   |   
| 12V Li-ion battery                                                                          | For powering the robot                    |   |   |   
