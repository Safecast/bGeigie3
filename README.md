## bGeigie3

These are the Eagle CAD files for the bGeigie v3.0 (codename NX) board.

This project is a part of the Safecast radiation monitoring project.
Find out more on [the Safecast website](http://www.safecast.org)

_Note_: although the github repo is named `bGeigie2`, the content is really the **bGeigie3**.

## License

2011-2013 (c) Robin Scheibler
Creative Commons Attribution-ShareAlike 3.0 Unported (CC BY-SA 3.0)
For more details see (http://creativecommons.org/licenses/by-sa/3.0/)

## Produce a bGeigie3

### Gerber

The gerber files can be downloaded [here](https://dl.dropboxusercontent.com/u/78009186/files/bGeigie_v3.4_gerber.zip)

### BOM

The full BOM can be found [here](https://docs.google.com/spreadsheet/ccc?key=0AvXZ3hGhBSusdEQ3NjlfN2hRUnljeTNhNEF5WDNzVWc&usp=sharing).

### Software

* [Firmware](https://github.com/Safecast/SafecastBGeigie)
* [Modded arduino IDE](https://github.com/fakufaku/Arduino) [bin](https://github.com/downloads/fakufaku/Arduino/arduino-Safecast-20121019-macosx.zip)
* [Automated programming tools](https://github.com/Safecast/SCbG3-hexes)

## Tech notes

### Power supply

The system is powered by a LiPo battery providing 4.2V at full charge and dies around 3.5V.

### Battery sensing

The Atmega1284p has two internal analog references: 1.1 or 2.56.

We need to sense the battery voltage between 4.2 and 3.5V.

Let's use a voltage divider with R1 = 100K and R2 = 120K.

Then `Vs = R2/(R1+R2) = 0.54*Vin`, giving a range of 2.3V to 1.89V roughly. We
decide to use the 2.5 reference. This gives use roughly 170 levels of
resolution.

### 50 Ohm trace for the Radio and GPS antennas

* Wiki entry on [microstrips](http://en.wikipedia.org/wiki/Microstrip)
* Microstrip impedance [calculator](http://www.cepd.com/calculators/microstrip.htm)

As a starting point, I used the following values based on [PCB Fusion](http://www.seeedstudio.com/depot/fusion-pcb-service-p-835.html?cPath=185).

* Trace width: 2.815mm (need to look-up tolerance of printing service)
* Substrate height: 1.6mm (standard from PCB Fusion)
* Copper thickness: 0.035mm (guessed from PCB Fusion characteristics, inner layer ?)

give an impedance Z=50.04 Ohms.

### Possible printing services

* [PCB Fusion](http://www.seeedstudio.com/depot/fusion-pcb-service-p-835.html?cPath=185)
* [PCB Cart](http://www.pcbcart.com/) (seems to offer manufacturing too)
* [PCB Express](http://www.pcbexpress.com/)

