# Advanced Airlock script

## Infos
The scripts follow a simple cycle when triggerd.
- Close door
- Depressurizing down to DEPRESSURE_PRECISION KPa (0 by default)
- Pressuring up to *External Pressure* minus PRESSURE_PRECISION KPa (10 by default)
- Open door

In this version, both doors can be opened if the atmosphere is similar on both sides of SAS. The notation *Indoor/Outdoor* indicates which doors should be closed if the atmosphere differs (always inside door to prevent pollution).

Only closed doors can trigger the cycle.

There are 5 statuses :
- *STATUS_VENT_OUTWARD* : Cycle to outside (-2)
- *STATUS_WAIT_OUTWARD* : Outside door are open (-1)
- *STATUS_OPEN* : Both door are open (0)
- *STATUS_WAIT_INWARD* : Inside door are open (1)
- *STATUS_VENT_INWARD* : Cycle to inside (2)

NB : The **Status Memory** is the law. If you change its value during a cycle the cycle stop according to the new value.

## Door Control
Script : [DoorControl](/Scripts/AdvancedAirlock/DoorControl)
- D0 : Status Memory
- D1 : Airlock Indoor
- D2 : Airlock Outdoor
- D3 : Light
- D4 : Sensor In
- D5 : Sensor Out

This script update **Status Memory** to trigger the cycle.
The status indicate which doors need to be *open/close*

- *STATUS_VENT_OUTWARD* : Wait with both doors closed
- *STATUS_WAIT_OUTWARD* : Wait trigger on inside door and open outside door
- *STATUS_OPEN* : Open both doors
- *STATUS_WAIT_INWARD* : Wait trigger on outside door and open inside door
- *STATUS_VENT_INWARD* : Wait with both doors closed

The light is **On** in *STATUS_VENT_OUTWARD* and *STATUS_VENT_INWARD* status.

The atmosphere is considered to be similar according to these constants :
- DIFF_TEMPERATURE : Maximum temperature difference (default 10K)
- DIFF_PRESSURE : Maximum pressure difference (default 10Kpa)
- DIFF_OXYGEN : Maximum O2 ratio difference (default 0.02)
- DIFF_CARBONDIOXIDE : Maximum CO2 ratio difference (default 0.01)
- DIFF_VOLATILES : Maximum H2 ratio difference (default 0.01)
- DIFF_POLLUTANT : Maximum X ratio difference (default 0.00001)

## Vent Control
Script : [VentControl](/Scripts/AdvancedAirlock/VentControl)
- D0 : Status Memory
- D1 : Vent In
- D2 : Vent Out
- D3 : Sensor SAS
- D4 : Sensor In
- D5 : Sensor Out

This script manage pressurization/depressurization cycle with respect to **Status Memory**.
When the cycle is done the **Status Memory** is set to *STATUS_WAIT_OUTWARD* if the previous state was *STATUS_VENT_OUTWARD* (or *STATUS_WAIT_INWARD* if *STATUS_VENT_INWARD*).

The *DEPRESSURE_PRECISION* and *PRESSURE_PRECISION* are set to increase the speed of a cycle by partially pressurizing/depressurizing the SAS and limiting excessive pressure differences.

## Diagram

It is recommended to place the sensor far enough from the vent ('cause during pressurization the pressure around the vent down to 0).
Especially if you have several SAS in a corridor.

![Airlock diagram](/Diagrams/Airlock.svg)
