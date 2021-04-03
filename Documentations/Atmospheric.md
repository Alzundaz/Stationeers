# Atmospheric script

## Infos
The script targets :
- Keep pressure in both tank under *MAX_PRESSURE*
- Activate filtration if **Waste Tank** has more than *MAX_MOLES* moles
- Keep O2 Ratio to *O2_RATIO*

The tanks can be manually dumped via a lever.

## Atmospheric
Script : [Atmospheric](/Scripts/Atmospheric)
- D0 : Waste Tank
- D1 : Waste Dump Pump
- D2 : Gas Mixer
- D3 : Atmospheric Tank
- D4 : Atmospheric Dump Pump
- D5 : Dump Lever (for manual dump, optional)

### Overpressure
If pressure in a tank is above *MAX_PRESSURE* the **Dump Pump** is activated until the pressure down under *MIN_PRESSURE*.
If the O2 ratio is above *O2_RATIO_MAX* of under *O2_RATIO_MIN* the **Dump Pump** is activated.

### Manual Dump
If **Lever** (optional) is activated the **Filtration** and **Gas Mixer** are stopped and all **Dump Pump** are activated.

### Filtration activation
If the number of moles in **Waste Tank** is greater than *MAX_MOLES* the filtration is activated until the number of moles down under *MIN_MOLES*.
The filtration activation is a batch writing so you can place more than one device to speed up filtration.

### O2 Ratio
The O2 Ratio set in **Gas mixer** is calculated like that :

***target + (target - ratio) * LOG(moles) * k***

With :
- ratio : O2 Ratio in tank
- target : *O2_RATIO* contant
- moles : Total moles in tank
- k : coefficient *KRATIO*

NB : If you reverse O2 and N inputs you need to set *REVERSED* to 1.

## Diagram

![Atmospheric diagram](/Diagrams/Atmospheric.svg)
