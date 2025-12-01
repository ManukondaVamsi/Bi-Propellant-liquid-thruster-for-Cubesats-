# CubeSat Bi-Propellant Thruster Design (N₂O₄ / MMH) – MATLAB Tool
This repository contains a **MATLAB design tool** for a **bi-propellant liquid rocket thruster** sized for **CubeSat-class spacecraft**.
The script computes key performance and design parameters using combustion data from your project report (CEA-derived), including:

* Thrust
* Mass flow rate
* Nozzle throat & exit areas
* Propellant budget (via Tsiolkovsky)
* Fuel & oxidizer split
* Burn time
* Tank volumes
* Feed system pressure requirements

This code is modular, easy to modify, and can be adapted for other propellant pairs, chamber pressures, or CubeSat configurations.

### Thruster Performance
* Computes thrust from chamber pressure and thrust coefficient (Cf)
* Computes exhaust velocity and Isp
* Mass flow rate from characteristic velocity (C*)

### Propellant Budgeting
* Uses the Tsiolkovsky equation to size total propellant mass
* Fuel/Oxidizer split via O/F ratio
* Custom CubeSat mass & ΔV input

### Nozzle Design
* Computes:

  * Throat area (At)
  * Exit area (Ae)
  * Throat/exit diameters
  * Expansion ratio (ε)

### Feed System Requirements
* Injector pressure drop
* Cooling-channel losses
* Piping losses
* Tank minimum pressure

### Tank Sizing
* Fuel & oxidizer volumes based on density
* CubeSat integration ready

## How the Code Works
The script is based on standard theoretical rocket equations and experimentally derived combustion data:
### 1️ Thruster Sizing
Uses:
[
T = C_f \cdot P_c \cdot A_t
]
### 2️ Nozzle Solver
Includes:
[
A_e = A_t \cdot \epsilon
]
### 3️ Mass Flow Rate
From characteristic velocity:
[
\dot{m} = \frac{P_c A_t}{C^*}
]
### 4️ Propellant Mass (Tsiolkovsky)
[
m_{prop} = m_0 \left(1 - e^{-\Delta V/V_e}\right)
]
### 5️ Feed Pressure Budget
[
P_{tank} = P_c + \Delta P_{injector} + \Delta P_{cooling} + \Delta P_{lines}
]

## How to Run
1. Clone the repository:
```bash
git clone https://github.com/yourusername/cubesat-biprop-thruster.git
```
2. Open MATLAB.
3. Run:
```matlab
biprop_cubesat_thruster
```
4. All results will print clearly in the Command Window
## Outputs
The script prints:
* Total propellant mass
* Fuel/Ox mass split (MMH / N₂O₄)
* Throat diameter (mm)
* Exit diameter (mm)
* Mass flow rate
* Burn time
* Tank volumes
* Required tank pressure

```
Total propellant mass = 0.212 kg
Fuel mass (MMH)       = 0.077 kg
Oxidizer mass (N2O4)  = 0.135 kg
Throat diameter dt    = 0.94 mm
Exit diameter de      = 11.52 mm
Required tank pressure = 18.2 bar
```

## Intended Use
This tool is ideal for:
* CubeSat propulsion system design
* Academic propulsion projects
* Concept studies & preliminary sizing
* Classroom demonstrations
* Liquid thruster system trade studies
* Regenerative cooling model
* Injector orifice sizing
* Mixture ratio optimization
* CEA automation integration
* Thermal design module

