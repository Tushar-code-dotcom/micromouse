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

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-0pky{border-color:inherit;text-align:left;vertical-align:top}
</style>
<table class="tg"><thead>
  <tr>
    <th class="tg-0pky">STM32F407VGT6</th>
    <th class="tg-0pky">Main microcontroller</th>
    <th class="tg-0pky"></th>
    <th class="tg-0pky"></th>
    <th class="tg-0pky"></th>
  </tr></thead>
<tbody>
  <tr>
    <td class="tg-0pky">N20 600 RPM Micro-Metal gear motor</td>
    <td class="tg-0pky">Motor for driving the robot</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky">LM2576 5V Output SMPS Switcher IC- HTC   Korea</td>
    <td class="tg-0pky">Stepping down voltage from 12V to 5V</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky">AMS 1117 3.3V LDO</td>
    <td class="tg-0pky">Stepping down voltage from 12V to 5V</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky">HM-BT4502 bluetooth module</td>
    <td class="tg-0pky">For wirelessly receiving data from the uC</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky">IR   Emitter/Receiver pair(could be replaced with more accurate and cheaper mmWave   radar)</td>
    <td class="tg-0pky">For sensing the distance from the walls</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky">12V Li-ion battery</td>
    <td class="tg-0pky">For powering the robot</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
</tbody></table>
