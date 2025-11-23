# Unit 1: Basic Electrical Concepts

## Electric Charge, Current, Voltage, Energy, and Power

*   **Electric Charge (Q):** The intrinsic property of matter responsible for electric and magnetic phenomena. It is quantized and conserved. The smallest unit of charge is the charge of a single electron, e = 1.602 x 10^-19 Coulombs (C).
*   **Electric Current (I):** The rate of flow of electric charge through a conductor. It is measured in Amperes (A), where 1 Ampere = 1 Coulomb/second.
    *   `I = dQ/dt`
*   **Voltage (V):** Also known as potential difference, it is the work required per unit of charge to move a test charge between two points. It is measured in Volts (V), where 1 Volt = 1 Joule/Coulomb.
    *   `V = dW/dQ`
*   **Energy (W):** The ability to do work. In an electric circuit, energy is supplied by sources and consumed by components. It is measured in Joules (J).
*   **Power (P):** The rate at which energy is transferred or work is done. It is measured in Watts (W), where 1 Watt = 1 Joule/second.
    *   `P = dW/dt = (dW/dQ) * (dQ/dt) = V * I`

## Independent and Dependent Sources

*   **Independent Sources:** Provide a specified voltage or current that is not dependent on any other variable in the circuit.
    *   **Ideal Voltage Source:** Maintains a constant voltage across its terminals, regardless of the current flowing through it.
    *   **Ideal Current Source:** Maintains a constant current flowing through it, regardless of the voltage across its terminals.
*   **Dependent Sources:** The output voltage or current depends on another voltage or current elsewhere in the circuit.
    *   **Voltage-Controlled Voltage Source (VCVS):** `V = μ * Vx`
    *   **Current-Controlled Voltage Source (CCVS):** `V = r * Ix`
    *   **Voltage-Controlled Current Source (VCCS):** `I = g * Vx`
    *   **Current-Controlled Current Source (CCCS):** `I = β * Ix`

## Ohm's Law

Ohm's law states that the voltage across a resistor is directly proportional to the current flowing through it, provided the temperature and other physical conditions remain unchanged.

*   `V = I * R`
    *   **V:** Voltage in Volts (V)
    *   **I:** Current in Amperes (A)
    *   **R:** Resistance in Ohms (Ω)

## Series and Parallel Resistors

*   **Resistors in Series:** When resistors are connected end-to-end, the total equivalent resistance is the sum of their individual resistances. The current is the same through all series resistors.
    *   `Req = R1 + R2 + ... + Rn`
*   **Resistors in Parallel:** When resistors are connected across the same two points, the reciprocal of the total equivalent resistance is the sum of the reciprocals of their individual resistances. The voltage is the same across all parallel resistors.
    *   `1/Req = 1/R1 + 1/R2 + ... + 1/Rn`

## Voltage and Current Division

*   **Voltage Divider Rule:** For resistors in series, the voltage across any one resistor is proportional to its resistance relative to the total resistance.
    *   `Vx = V_total * (Rx / R_total)`
*   **Current Divider Rule:** For resistors in parallel, the current through any one branch is inversely proportional to its resistance.
    *   `Ix = I_total * (R_total / Rx)` (where R_total is the equivalent resistance of the parallel combination).

## Ideal and Real Circuit Elements

*   **Ideal Elements:** Mathematical abstractions with perfect properties (e.g., an ideal resistor has only resistance, an ideal wire has zero resistance, an ideal voltage source has zero internal resistance).
*   **Real Elements:** Practical components have imperfections. A real resistor has some stray capacitance and inductance, a real wire has resistance, and a real voltage source has internal resistance which causes the terminal voltage to drop as the current increases.

## Source Transformations

A practical voltage source (a voltage source `Vs` in series with a resistor `R`) can be converted into an equivalent practical current source (a current source `Is` in parallel with the same resistor `R`), and vice versa. This is a powerful circuit simplification technique.

*   `Vs = Is * R`
*   `Is = Vs / R`
The resistor `R` has the same value in both configurations.

## Kirchhoff's Laws

*   **Kirchhoff's Current Law (KCL):** Based on the principle of conservation of charge, it states that the algebraic sum of all currents entering and exiting a node (or any closed boundary) must be zero.
    *   `Σ I_entering = Σ I_leaving`
*   **Kirchhoff's Voltage Law (KVL):** Based on the principle of conservation of energy, it states that the algebraic sum of all the voltage drops and rises around any closed loop in a circuit must be zero.
    *   `Σ V_rises = Σ V_drops`

## Basic Circuit Modeling

The process of creating a simplified representation (a circuit diagram) of a real-world electrical system. This involves:
1.  Identifying the key components of the system.
2.  Representing them with ideal circuit elements (resistors, capacitors, inductors, sources).
3.  Connecting the elements to reflect their physical connections in the actual system.

## Practical Resistor Behavior

*   **Temperature Dependence:** The resistance of most materials changes with temperature. The temperature coefficient of resistance (TCR) describes this change.
*   **Power Rating:** Resistors can only dissipate a certain amount of power as heat before they are damaged. This maximum power is called the power rating.
*   **Frequency Dependence:** At high frequencies, a real resistor exhibits parasitic capacitance and inductance, causing its impedance to deviate from its pure resistance value.

## Power Calculations in Resistive Circuits

The power dissipated by a resistor can be calculated using any of the following formulas derived from Ohm's Law and the basic power formula (`P=VI`):

*   `P = V * I`
*   `P = I^2 * R`
*   `P = V^2 / R`

In any resistive circuit, the total power supplied by the sources must equal the total power dissipated by all the resistors in the circuit.
