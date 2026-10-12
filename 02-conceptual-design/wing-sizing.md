# Wing Sizing (Baseline Calculations)

### Knowns:
W = MTOW (Maximum Take-off Weight) [REQ-03] * g = 1.36 kg * 9.81 m/s^2 = 13.3416 N\
ρ (Air density) = 1.225 kg/m^3 [AS-04] \
C_L Max = 1.0 [AS-03]

### Part 1: Validating Reference Data:
Reference QuadPlane [1] data: mass = 1.68 kg, wingspan = 1.22 m, chord = 0.15 m, stall speed = 11.9 m/s\
W = 1.68 kg * 9.81 m/s^2 = 16.481 N\
A = 1.22 m * 0.15 m = 0.183 m^2\
C_L Max = 2W / (ρ * V_stall^2 * A) = 1.038 (dimensionless)\
The calculated reference C_L Max is 1.038, which is consistent with AS-03, the C_L Max of 1.0 determined from the coefficient plots from reference data.\
Wing loading = 1.68 / 0.183 = 9.180 kg/m^2

### Part 2: My Baseline Wing Calculations:
Baseline assumptions: wingspan = 1.2 m [AS-01], chord = 0.2 m [AS-02] \
A = 1.2 * 0.2 = 0.24 m^2\
V_stall = sqrt(2W / (ρ * C_L Max * A)) = 9.527 m/s\
Wing loading: 1.36 / 0.24 = 5.667 kg/m^2

### Comparison:
| Aircraft | Mass (kg) | Wing Area (m^2) | Wing Loading (kg/m^2) | Stall Speed (m/s) |
|---|---|---|---|---|
| Reference Quadplane [1] | 1.68 | 0.183 | 9.180 | 11.9 |
| My Baseline | 1.36 | 0.24 | 5.667 | 9.527 |

### Conclusion:
My baseline design is better for beginners than the Reference QuadPlane [1]. 
My baseline has a wing loading of about 38% lower and a stall speed of 2.4 m/s less than the reference.
This means that there is a smoother transition from hover to cruising and less kinetic energy at stall speed, which means less damage to the aircraft in the case of a crash.
However, the trade-offs are a larger wing and higher sensitivity to gusts of wind.

### Notes:
Lift equation: L = 1/2 * ρ * V^2 * C_L * A      (Either "A" or "S" is used as a variable for Wing Area)\
Reordering for velocity: V = sqrt(2L / (ρ * C_L * A))\
At an aircraft's stall speed, lift is equal to the weight, giving: V_stall = sqrt(2W / (ρ * C_L Max * A))
When solving for the max coefficient of lift, this can be written as: C_L Max = 2W / (ρ * V_stall^2 * A)
