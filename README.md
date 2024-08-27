# Powerline-USB-C
Powerline is a small 3HP Front Entry USB C Eurorack power supply.
![Alt text](Powerline-USB-C/Powerline-USB-C.svg?raw=true "Schematic")
## Repository Layout
The Frontpanel and main PCB have a Kicad project with footprint and symbol libraries.
The main PCB also includes a 3D render of the Frontpanel as a Footprint
## Specs
- 12V 1000mA
- -12V 300mA
- 5V 1000mA
## Features
Powerline uses the cheap and readily available CH224k IC to get 20V over USB-C PD. The power brick used should be able to supply at least 2A of current at that voltage (40W Charger and above should be fine).
The 20V then gets regulated to a dual +/-12V and 5V supply by two N7812-1C and an N7805-1C and can be accessed by one 16-pin Power header. You can also omit the 5V rail and solder a 10pin header if none of your modules need 5V.
Powerline uses a single LED powered by the 12V rail to indicate power.
The PCBs are designed to jlcpcbs 2 Layer design capabilities to be compatible with most cheap PCB services.
## Parts List:
The only difficult-to-source parts are the USB-C connector and regulator ICs. I got both from Digikey.
I also recommend sourcing the CH224k from a reputable supplier like LCSC to avoid broken parts.
You also need two M2 5mm standoffs and 4 M2 screws that fit the standoffs (max. 4mm) to assemble the Module.
|Part Number|Value|Information|
|---|---|---|
|C1|0805 1uF 50V X7R|Decoupling Capacitor for the CH224K|
|C2, C4|1210 10uF 50V X7R|Input Cap for the regulator|
|C3, C5|1210 22uF 25V X7R|Output cap for the regulator|
|D2|3mm LED|3mm radial LED with a nice color|
|J1|Molex-2171780001|I selected this because of its very good availability. You can even look at the Molex website to see where there is stock!|
|J2, J3|Power header|A 02x08 2.54mm pin spacing vertical through hole pin header, do yourself a favor and get a keyed one|
|L1|1210 10uH|Look out for a rated current of above 600mA|
|R1|0603 1k|Current limiting resistor for the CH224Ks Powersupply|
|R2|0603 5k1|Current limiting resistor for the LED: if it's too bright, pick a higher resistance.|
|U1|CH224K|The PD trigger IC|
|U2, U3|N7912-1C|+/-12V regulators|
|U4|N7805-1C|5V regulator|
## Build guide
TODO
