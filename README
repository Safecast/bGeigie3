## Readme

This is the Eagle CAD files for the bGeigie v2.0 (codename Delta) board.

This project is a part of the Safecast radiation monitoring project.
Find out more on [the Safecast website](http://www.safecast.org)

### License

2011 (c) Robin Scheibler
Creative Commons Attribution-ShareAlike 3.0 Unported (CC BY-SA 3.0)
For more details see (http://creativecommons.org/licenses/by-sa/3.0/)

## Design

### Main microcontroller

Atmega1284p.

### Power supply

The system is powered by a LiPo battery providing 4.2V at full charge and dies around 3.5V.

### Battery sensing

The Atmega1284p has two internal analog references: 1.1 or 2.56.

We need to sense the battery voltage between 4.2 and 3.5V.

Let's use a voltage divider with R1 = 300K and R2 = 100K.

Then Vs = R2/(R1+R2) = 1/4*Vin, giving a range of 1.05 to 0.875V roughly. We
decide to use the 1.1 reference. This gives use roughly 160 levels of
resolution.
