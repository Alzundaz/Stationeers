# Clock script

## Infos
This script can display :
- Clock : based on daylight sensor
- Battery Time Left : based on batteries charge variation
- Battery clock : based on Battery Time Left and Clock time

The value DAYTIME determine the duration of a day (to display) in hours.
Default value is 20 for a day of 20 hours (or 20 minutes IRL).
The values CHARGECOLOR/DISCHARGECOLOR are color for dis/charging.
Default values are *green* for *charging* and *orange* for *discharging*.
The format display is the classical HH.MM (MM.SS IRL)

## Script
Script : [Clock](/Scripts/Clock)

- D0 : Daylight Sensor
- D1 : Clock Display
- D2 : Battery Time Left Display
- D3 : Battery Clock Display

NB : The daylight sensor must be installed vertically facing east.

## Diagram

![Clock](/Diagrams/Clock.svg)
