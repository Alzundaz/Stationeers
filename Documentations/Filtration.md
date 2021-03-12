# Filtration script

## Infos
Script to manage filtration system like activate/deactivate filtration, overpressure discharge and keep a target pressure in the distribution circuit.

## Script
Script : [Filtration](/Scripts/Filtration)

- D0 : Tank
- D1 : Dump pump for overpressure
- D2 : Inlet gas analyzer (can be a tank)
- D3 : Filtration
- D4 : Gas analyser on distribution circuit
- D5 : Volum Pump on distribution circuit

### Dump Status
The tank is dump when pressure reached over MAXPRESSURE. The dump keep doing until the pressure down below MINPRESSURE.

### Filtration Status
The filtration is activated when the number of mols (according to filters in filtration) reached over MAXMOLES. The filtration keep activate until this value down below MINMOLES.

### Distribution Status
The distribution pump is activated when the pressure in distribution is below MINDISTRIBUTION. The pump keep  activate until this value reached MAXDISTRIBUTION.

## Diagram

![Filtration diagram](/Diagrams/Filtration.svg)
