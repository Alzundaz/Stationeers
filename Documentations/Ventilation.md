# Ventilation script

## Infos
The script targets :
- Temperature of 20°C
- Pressure of 101 KPa
- O2 ratio of 20%

It also keeps a small stream to avoid fixed pollution.
Different factor (for each gas) modify the stream.
The more polluted the air, the more air is evacuated.
Ditto if the air deviates from the température and O2 target.

## Repeater
Script : [Repeater](/Scripts/Miscellaneous/Repeater)
- D0 : Lever

Instead of using an IC, you can use a batchWriter to write Setting in all ICs.
The use of Repeater Script is only for selecting affected ICs.

## Vent Control
Script : [Ventilation](/Scripts/Ventilation)
- D0 : Sensor 1
- D1 : Vent In 1
- D2 : Vent Out 1
- D3 : Sensor 2
- D4 : Vent In 2
- D5 : Vent Out 2

Each IC can control two pairs of vents and use two sensors. You can use the same sensor (read only).

The script handle both parts separately (D0,D1,D2 and D3,D4, D5)
You can connect two vents and a sensor in only one side without any crash.

## Diagram

![Ventilation diagram](/Diagrams/Ventilation.svg)
