 # Powerline-USB-C
Powerline is a small 3HP Front Entry USB C Eurorack power supply.
![Alt text](Powerline-USB-C/3D-Powerline-USB-C.png?raw=true "3D render")
## Repository Layout
The Frontpanel and main PCB have a Kicad project with footprint and symbol libraries.
The main PCB also includes a 3D render of the Frontpanel as a Footprint
## Specs
- 12V 1000mA
- -12V 300mA
- 5V 1000mA
## Features
Powerline uses the cheap and readily available CH224k IC to get 20V over USB-C PD. The power brick should supply at least 2A of current at that voltage (40W Charger and above should be fine).
The 20V then gets regulated to a dual +/-12V and 5V supply by two N7812-1C and an N7805-1C and can be accessed by one 16-pin Power header. You can also omit the 5V rail and solder a 10pin header if none of your modules need 5V.
Powerline uses a single LED powered by the 12V rail to indicate power.
The PCBs are designed to jlcpcbs 2 Layer design capabilities to be compatible with most cheap PCB services.
## Parts List
The only difficult-to-source parts are the USB-C connector and regulator ICs. I got both from Digikey.
I also recommend sourcing the CH224k from a reputable supplier like LCSC to avoid broken parts.
You also need two M2 5mm standoffs and 4 M2 screws that fit the standoffs (max. 4mm) to assemble the Module.
![Alt text](Powerline-USB-C/Powerline-USB-C.svg?raw=true "Schematic")
|Part Number|Value|Information|
|---|---|---|
|C1, C8|0805 1uF 50V X7R|Decoupling Capacitors|
|C2, C4, C6|1210 10uF 50V X7R|Input Cap for the regulator|
|C3, C5, C7|1210 22uF 25V X7R|Output cap for the regulator|
|D1|3mm LED|3mm radial LED with a nice color|
|J1|MC-802YC-H105|Female USB-C connector|
|J2|Power header|A 02x08 2.54mm pin spacing vertical through hole pin header|
|L1|1210 10uH|Look out for a rated current of above 600mA|
|R1|0603 5k1|Current limiting resistor for the LED: if it's too bright, pick a higher resistance|
|R2|0604 10k|VBUS sense resistor|
|U1|CH224K|The PD trigger IC|
|U2, U3|N7912-1C|+/-12V regulators|
|U4|N7805-1C|5V regulator|
|U5|HT7533-1|3.3V regulator|
|Standoffs|m2 5-7.5mm|You need 2 Standoffs and 4 screws to mount the Module to its front plate
## Build Guide
The PCB doesn't include any Thermal reliefs so that soldering can be tricky with a weak iron or small tip. I did everything with a 60W and 4mm Bevel Tip on a TS100 with extra Flux. You do not need additional equipment as the CH224K is solderable from the bottom. I used 7.5mm Standoffs, which protects the USB-C connector nicely. I would recommend soldering the USB-C connector last.