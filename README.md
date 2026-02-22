# Two‑Compartment PK/PD Model with Emax Effect – MATLAB

This project simulates the time course of drug concentrations in a two‑compartment pharmacokinetic (PK) model after an IV bolus dose and links the central concentration to
a pharmacodynamic (PD) effect using a sigmoidal Emax model. The code solves the differential equations and generates two figures overlaying concentration(s) and effect.

## What I Built

- **Two‑compartment PK model**:
  - Central compartment (volume `V1`, elimination clearance `CL`)
  - Peripheral compartment (volume `V2`, inter‑compartmental clearance `Q`)
  - IV bolus dose `D` administered into the central compartment.
- **PD model**: Emax model linking central concentration `C1` to effect `E`:
  `E = (Emax * C1^n) / (EC50^n + C1^n)`
- **Numerical solution**: MATLAB’s `ode23` solves the ODE system over 24 hours.
- **Visualization**:
  - **Figure 1**: Central concentration (left y‑axis) and effect (right y‑axis) vs. time.
  - **Figure 2**: Central and peripheral concentrations (left y‑axis) and effect (right y‑axis) vs. time.
  - Uses `yyaxis` to overlay PK and PD on the same axes, clearly showing their relationship.
<img width="560" height="338" alt="image" src="https://github.com/user-attachments/assets/ed4dc165-c6a1-4ae5-8ae6-006e88ab0c30" />
<img width="560" height="338" alt="image" src="https://github.com/user-attachments/assets/f5883a92-865c-4b6e-aa90-196ce4011f6f" />


## Skills Demonstrated

- MATLAB programming (scripting, function handling, ODE solvers)
- Advanced pharmacokinetic modeling (two‑compartment, IV bolus)
- Pharmacodynamic modeling (Emax model, sigmoidicity)
- Numerical solution of differential equations (`ode23`, `deval`)
- Data visualization (multiple plots, `yyaxis`, custom line styles, legends)
- Parameter organization (passing parameter vectors to ODE functions)

## How to Run

1. Ensure both the driver script and the function `WK3_Class_4_103` (which defines the two‑compartment ODEs) are in the same folder or on your MATLAB path.
2. Open the script (e.g., `TwoComp_PKPD_IVBolus.m`) in MATLAB.
3. Click **Run** or type the filename in the Command Window.
4. Modify parameters at the top of the script (`D`, `CL`, `V1`, `Q`, `V2`, `Emax`, `EC50`, `n`) to explore different scenarios.

**Note**: The ODE function `WK3_Class_4_103` must have the signature `dAdt = function(t, A, THETA)`, where `THETA = [CL, V1, Q, V2]`. If you don’t have this function, you can create it as shown below.

