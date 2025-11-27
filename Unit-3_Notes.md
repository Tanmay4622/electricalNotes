# Unit 3: AC Circuit Analysis

## 1. Fundamentals of AC Signals

### 1.1. Sinusoidal Signals and Phasors
AC (Alternating Current) circuits are driven by sinusoidal voltage and current sources. A sinusoidal signal in the time domain is represented as:
`v(t) = Vm * cos(ωt + φ)`
- `Vm`: Amplitude (peak value)
- `ω`: Angular frequency (in rad/s), `ω = 2πf`
- `φ`: Phase angle

To simplify analysis, we use **phasors**. A phasor is a complex number that represents the amplitude and phase angle of a sinusoidal signal in the frequency domain.
- Time Domain: `v(t) = Vm * cos(ωt + φ)`
- Phasor (Frequency) Domain: `V = Vm∠φ = Vm * e^(jφ)`

Using phasors converts differential equations (time domain) into linear algebraic equations (frequency domain), which are much easier to solve.

## 2. AC Circuit Components and Analysis

### 2.1. Impedance (Z) and Admittance (Y)
- **Impedance (Z):** The total opposition to current flow in an AC circuit. It's the frequency-domain equivalent of resistance and is a complex quantity measured in Ohms (Ω). `Z = R + jX`
  - `R`: Resistance (real part)
  - `X`: Reactance (imaginary part)
- **Impedances of Basic Components:**
  - Resistor (R): `Z_R = R`
  - Inductor (L): `Z_L = jωL` (Reactance is positive)
  - Capacitor (C): `Z_C = 1 / (jωC) = -j / (ωC)` (Reactance is negative)
- **Admittance (Y):** The reciprocal of impedance, analogous to conductance. `Y = 1/Z = G + jB`
  - `G`: Conductance
  - `B`: Susceptance

### 2.2. Node and Mesh Analysis in Phasor Domain
Standard circuit analysis techniques can be applied in the frequency domain using phasors and impedances.
- **Node Analysis:** Based on Kirchhoff's Current Law (KCL). Write KCL equations for each node using phasor currents and admittances.
- **Mesh Analysis:** Based on Kirchhoff's Voltage Law (KVL). Write KVL equations for each mesh using phasor voltages and impedances.

## 3. Power in AC Circuits

### 3.1. Instantaneous, Average, and Reactive Power
- **Instantaneous Power:** `p(t) = v(t) * i(t)`
- **Average Power (P):** The real power dissipated by the circuit, typically by resistors. It represents the useful energy consumed. Its unit is the **Watt (W)**.
  `P = V_rms * I_rms * cos(θ)` where `θ` is the angle difference between voltage and current.
- **Reactive Power (Q):** The power that is stored and returned by reactive components (inductors and capacitors). It does no real work. Its unit is the **Volt-Amp Reactive (VAR)**.
  `Q = V_rms * I_rms * sin(θ)`

### 3.2. Complex Power and Power Factor
- **Complex Power (S):** A complex quantity that combines average and reactive power.
  `S = P + jQ`
- **Apparent Power (|S|):** The magnitude of the complex power. Its unit is the **Volt-Amp (VA)**.
  `|S| = sqrt(P² + Q²) = V_rms * I_rms`
- **Power Factor (pf):** The ratio of average power to apparent power. It indicates how effectively the current is being converted into useful work.
  `pf = P / |S| = cos(θ)`
  - **Lagging pf:** Current lags voltage (inductive load, θ > 0).
  - **Leading pf:** Current leads voltage (capacitive load, θ < 0).
- **Power Factor Correction:** The process of improving the power factor (making it closer to 1) by adding capacitors in parallel with an inductive load. This reduces the total current drawn from the source, decreasing losses and improving system efficiency.

## 4. Resonance

Resonance occurs in an RLC circuit when the inductive and capacitive reactances cancel each other out (`X_L = X_C`). The frequency at which this happens is the **resonant frequency (ω₀)**.
`ω₀ = 1 / sqrt(LC)` rad/s
- **Series Resonance:** The circuit has minimum impedance (`Z = R`) and maximum current.
- **Parallel Resonance:** The circuit has maximum impedance and minimum current.

## 5. Three-Phase Circuits

A system of three AC voltages that are equal in magnitude and 120° out of phase with each other. This is the standard for power generation and distribution.

### 5.1. Balanced Circuits and Phase Sequence
- **Balanced Circuit:** A three-phase system where the sources are 120° apart with equal magnitude, and the loads in each phase are identical.
- **Phase Sequence:** The order in which the phase voltages reach their peak values. It can be positive (ABC) or negative (ACB).

### 5.2. Line and Phase Quantities
Two common connections for sources and loads are Wye (Y) and Delta (Δ).
- **Phase Quantities:** Voltage or current associated with a single phase (e.g., `V_AN`, `I_AB`).
- **Line Quantities:** Voltage between two lines or current in a single line (e.g., `V_AB`, `I_A`).

**Relationships for Balanced Systems:**
- **Wye (Y) Connection:**
  - `V_L = sqrt(3) * V_ph`
  - `I_L = I_ph`
- **Delta (Δ) Connection:**
  - `V_L = V_ph`
  - `I_L = sqrt(3) * I_ph`

### 5.3. Power in Three-Phase Loads
The total power in a balanced three-phase load is the sum of the power in the individual phases.
- **Total Average Power (P_T):** `P_T = 3 * V_ph * I_ph * cos(θ) = sqrt(3) * V_L * I_L * cos(θ)`
- **Total Reactive Power (Q_T):** `Q_T = sqrt(3) * V_L * I_L * sin(θ)`
- **Total Complex Power (S_T):** `S_T = sqrt(3) * V_L * I_L ∠θ`