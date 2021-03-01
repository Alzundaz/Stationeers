# Suit script
Script : [Suit](/Scripts/Suit)

This is a simple script to automatically close / open the helmet from the external environment.

## Polluant
If a pollutant is detected, the environment is considered dangerous and the helmet is closed.

## O2 Ratio
The minimum O2 ratio is calculated from an affine function.
The coefficient equal to -1.18 and the constant equal to 139.
These values are calculated from two points where the air is breathable (100% at 33 KPa and 20% at 101 KPa).
The result of the function is a percentage, so the script divides it by 100 to get a ratio (between 0 and 1).
The minimum 02 ratio is 5% and the maximum is 100%.

## Temperature
The temperature is acceptable if it is between 5°C and 40°C
