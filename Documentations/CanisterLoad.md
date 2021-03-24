# Filtration script

## Infos
This script can control the loading of 3 canisters.
Each pair is controlled only if both devices are connected (analyzer and pump).

NB : You can use a gas mixer instead of the volum pump.

## Script
Script : [CanisterLoad](/Scripts/CanisterLoad)

- D0 : Pipe Analyzer 1
- D1 : Volum Pump 1
- D2 : Pipe Analyzer 2
- D3 : Volum Pump 2
- D4 : Pipe Analyzer 3
- D5 : Volum Pump 3

The constants *FIRSTTARGETPREESSURE*, *SECONDTARGETPRESSURE* and *THIRDTARGETPRESSURE* define the target pressure for each pair.

## Diagram

![Canister Load diagram](/Diagrams/CanisterLoad.svg)
