# Airlock script

## Infos
The scripts follow a simple cycle when triggerd.
- Close door
- Depressurizing down to DEPRESSURE_PRECISION KPa (0 by default)
- Pressuring up to *External Pressure* minus PRESSURE_PRECISION KPa (10 by default)
- Open door

Only closed doors can trigger the cycle.

The notation *Indoor/Outdoor* indicates which doors are to be closed during initialization.
This will be more important in the advanced versions. Like keeping the SAS open if there is the same atmosphere on each side and close right door on depressurisation or pollution.

## Door Control
Script : [DoorControl](/Scripts/Airlock/DoorControl)
- D0 : Status Memory
- D1 : Airlock Indoor
- D2 : Airlock Outdoor
- D3 : Light

This script update **Status Memory** to trigger the cycle.
The status depend on which door is trigger (only closed door can be triggered).

- 0 : Waiting trigger
- 1 : Inward
- 2 : Outward

The light is **On** in other status than 0.

## Vent Control
Script : [VentControl](/Scripts/Airlock/VentControl)
- D0 : Status Memory
- D1 : Vent In
- D2 : Vent Out
- D3 : Sensor SAS
- D4 : Sensor In
- D5 : Sensor Out

This script manage pressurization/depressurization cycle with respect to **Status Memory**.
When the cycle is done the **Status Memory** is reset to 0.

The *DEPRESSURE_PRECISION* and *PRESSURE_PRECISION* are set to increase the speed of a cycle by partially pressurizing/depressurizing the SAS and limiting excessive pressure differences.

## Diagram

It is recommended to place the sensor far enough from the vent ('cause during pressurization the pressure around the vent down to 0).

![Airlock diagram](/Diagrams/Airlock.svg)
