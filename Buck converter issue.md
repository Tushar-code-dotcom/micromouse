I am not sure which of these issue could be the root cause of my DC-DC step down converter not working so I will list them one by one

### 1. Soldering at a higher temperature

I have soldered the buck converter, with a hot air gun at a temperature of 350 degree celsius for roughly 30 seconds-1 minute, I have resorted to such high temperatures, because a considerable amount of solder had to be melted before placing the IC on the PCB

![[Pasted image 20260210220326.png]]

![[WhatsApp Image 2026-02-10 at 10.07.25 PM.jpeg]]


#### **The issue**
Maybe the exposure to such temperature(350 deg C) could have caused the IC, to not work at all, because I was getting no input at the feedback pin

![[Pasted image 20260210225434.png]]
### 2. Using LTSpice model of TI instead of HTC korea to simulate
Maybe this is a bigger blunder considering that I have bought an HTC LM2576 regulator and am uisng the TI LTSpice model(due to lack of response of HTCKorea to send the model).

I thought the general characteristics would be the same, and maybe there would be a few slight variations in the ripple current
### 3. I have not tested the IC before soldering

I did not do any sort of time domain analysis, as I do not know how to build the test circuit, nor is there any test circuit provided by HTC Korea, TI has a thorough documentation on how to test their LM2576, but again since they are different companies, I didn't want to do that.

### 4. Did not follow the recommended output capacitor value

	I know this is a big issue, in terms of output ripple voltage but, since there was little to no output voltage on the AMS1117 3.3V IC, I had used an NI-DAQ to measure the output votlage but I was not able to get any value


### 5. RMS ripple current rating of the input capacitor

I have used a 100uF input capacitor  as recomendded by the datasheet
The datasheet recommends the RMS ripple current rating of the capacitor to be greater than `1.2 × (tON/T) × ILOAD` . I have not looked into ripple current rating of the capacitor

```
RMS ripple current= 1.2 × (tON/T) × ILOAD where 
tON/T = VOUT/VIN for a buck regulator
```
I selected the catch diode properly with a reverse voltage rating of 1.2 times greater than the maximum load current.






