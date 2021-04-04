# Solar Panel script

## Infos
This script control all solar panels on the grid.
Efficiency is close to 100% (exactly 99.3%).
The value AHEAD_COEFF keep the solar panel in advance of the sun.
If the total charge falls below MIN_CHARGE the solar panels return to their initial position to wait for the next sunrise.

NB : Solar panels should be placed so that the null position (0:0) faces east.

## Solar Panel
Script : [SolarPanel](/Scripts/SolarPanel)
- D0 : Daylight Sensor

NB : The daylight sensor must be installed horizontally with the top facing north  (as on the diagram).

## Diagram

![SolarPanel diagram](/Diagrams/SolarPanel.svg)
