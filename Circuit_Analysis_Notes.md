# Circuit Analysis Techniques

This document provides detailed notes on fundamental circuit analysis theorems and techniques.

## 1. Nodal Analysis

Nodal analysis is a method for determining the voltage (potential difference) between "nodes" (points where elements or branches connect) in an electrical circuit.

**Theory:**
Nodal analysis is based on Kirchhoff's Current Law (KCL), which states that the algebraic sum of currents entering a node must equal zero. The procedure is as follows:

1.  **Identify Nodes:** Identify all the nodes in the circuit. A node is a point where two or more circuit elements are connected.
2.  **Select a Reference Node:** Choose one node as the reference node (or ground). This node will have a potential of 0V. The choice of reference node is arbitrary, but it's often convenient to choose the node with the most connections.
3.  **Assign Node Voltages:** For all the remaining N-1 nodes, assign a voltage variable (e.g., V1, V2, ...). These voltages are measured with respect to the reference node.
4.  **Apply KCL at Each Non-Reference Node:** For each of the N-1 non-reference nodes, write an equation based on KCL. Assume that all unknown currents are leaving the node. The current flowing through a resistor is calculated using Ohm's Law (I = (V_start - V_end) / R).
5.  **Solve the System of Equations:** Solve the resulting system of linear equations to find the unknown node voltages.

**Statement (Kirchhoff's Current Law):**
> The algebraic sum of all currents entering and leaving a node must be equal to zero.
> ΣI_in = ΣI_out

## 2. Mesh Analysis

Mesh analysis (or the mesh current method) is a technique used to determine the currents flowing in the loops or meshes of a planar circuit.

**Theory:**
Mesh analysis is based on Kirchhoff's Voltage Law (KVL), which states that the algebraic sum of all voltages around any closed loop in a circuit is equal to zero.

1.  **Identify Meshes:** Identify all the meshes in the circuit. A mesh is a loop that does not contain any other loops within it.
2.  **Assign Mesh Currents:** Assign a current variable to each mesh (e.g., I1, I2, ...), assuming a clockwise or counter-clockwise direction.
3.  **Apply KVL to Each Mesh:** For each mesh, write an equation based on KVL. The voltage drops across resistors are calculated using Ohm's Law (V = IR). When a resistor is shared between two meshes, the current through it is the algebraic sum or difference of the two mesh currents.
4.  **Solve the System of Equations:** Solve the resulting system of linear equations for the unknown mesh currents.

**Statement (Kirchhoff's Voltage Law):**
> The algebraic sum of the potential rises and drops around any closed loop is zero.
> ΣV = 0

## 3. Linearity and Superposition Theorem

### Linearity
**Theory:**
Linearity is the property of a circuit where the output is directly proportional to the input. A circuit is linear if it consists of linear elements (resistors, capacitors, inductors) and linear dependent sources. For a linear circuit, the principles of homogeneity and additivity hold true.

*   **Homogeneity:** If the input is scaled by a factor 'k', the output is also scaled by the same factor 'k'.
*   **Additivity:** The response to a sum of inputs is the sum of the responses to each input applied individually.

### Superposition Theorem
**Statement:**
> In any linear, bilateral network containing multiple independent sources, the current through or voltage across any element is the algebraic sum of the currents or voltages produced by each independent source acting alone, with all other independent sources turned off (voltage sources replaced by a short circuit and current sources by an open circuit).

**Procedure:**
1.  Select one independent source to be active.
2.  Deactivate all other independent sources:
    *   Replace independent voltage sources with a short circuit (0V).
    *   Replace independent current sources with an open circuit (0A).
    *   *Dependent sources are not deactivated.*
3.  Calculate the desired voltage or current due to the single active source.
4.  Repeat steps 1-3 for each independent source in the circuit.
5.  The total voltage or current is the algebraic sum of the values calculated in each step.

## 4. Thevenin's Theorem

**Statement:**
> Any linear, two-terminal circuit can be replaced by an equivalent circuit consisting of a single voltage source (Vth) in series with a single resistor (Rth).

**Theory:**
Thevenin's theorem simplifies a complex portion of a circuit into a very simple equivalent form.

*   **Thevenin Voltage (Vth):** This is the open-circuit voltage at the two terminals of interest. It is the voltage that appears across terminals A and B when nothing is connected to them.
*   **Thevenin Resistance (Rth):** This is the equivalent resistance of the circuit looking back from the two terminals, with all independent sources turned off (voltage sources shorted, current sources opened).

**Procedure to find Vth and Rth:**
1.  **Find Vth:** Remove the load resistor (or the component connected to the terminals). Calculate the voltage across the open terminals (A and B). This is Vth.
2.  **Find Rth:** Deactivate all independent sources (voltage sources to short, current sources to open). Calculate the equivalent resistance between the terminals A and B. This is Rth.
3.  **Draw the Equivalent Circuit:** The Thevenin equivalent circuit is the voltage source Vth in series with the resistor Rth.

## 5. Norton's Theorem

**Statement:**
> Any linear, two-terminal circuit can be replaced by an equivalent circuit consisting of a single current source (In) in parallel with a single resistor (Rn).

**Theory:**
Norton's theorem is the dual of Thevenin's theorem. It provides an equivalent circuit using a current source and a parallel resistor.

*   **Norton Current (In):** This is the short-circuit current at the two terminals. It is the current that flows through a shorting wire placed between terminals A and B.
*   **Norton Resistance (Rn):** This is identical to the Thevenin resistance (Rn = Rth). It is the equivalent resistance looking back from the terminals with all independent sources turned off.

**Procedure to find In and Rn:**
1.  **Find In:** Place a short circuit across the terminals A and B. Calculate the current flowing through this short. This is In.
2.  **Find Rn:** Deactivate all independent sources and calculate the equivalent resistance between the terminals A and B. This is Rn.
3.  **Draw the Equivalent Circuit:** The Norton equivalent circuit is the current source In in parallel with the resistor Rn.

**Source Transformation:**
Thevenin and Norton equivalent circuits are related:
*   Vth = In * Rn
*   In = Vth / Rth
*   Rth = Rn

## 6. Maximum Power Transfer Theorem

**Statement:**
> For a DC voltage source with an internal resistance (or a Thevenin equivalent circuit), the maximum power is delivered to a load resistor (RL) when the load resistance is equal to the source resistance (or the Thevenin resistance, Rth).
> RL = Rth

**Theory:**
This theorem is crucial for applications where the efficiency of power transfer is paramount, such as in communication systems or power amplifiers. The power delivered to the load is given by:

P_L = I^2 * RL = (Vth / (Rth + RL))^2 * RL

To find the maximum power, we take the derivative of P_L with respect to RL and set it to zero, which yields the condition RL = Rth.

The maximum power transferred is then:
P_max = (Vth / (2 * Rth))^2 * Rth = Vth^2 / (4 * Rth)

## 7. Circuit Simplification Strategies

Effective circuit analysis often relies on simplifying the circuit before applying complex theorems.

*   **Series and Parallel Resistors:**
    *   **Series:** Resistors are in series if they share a single node and carry the same current. The equivalent resistance is the sum: Req = R1 + R2 + ...
    *   **Parallel:** Resistors are in parallel if they are connected across the same two nodes. The reciprocal of the equivalent resistance is the sum of the reciprocals: 1/Req = 1/R1 + 1/R2 + ...

*   **Source Transformation:** As mentioned earlier, a voltage source in series with a resistor can be converted into a current source in parallel with the same resistor, and vice-versa. This is a powerful tool for rearranging and simplifying circuits.

*   **Delta-Wye (Δ-Y) or Pi-Tee (Π-T) Transformation:**
    *   This transformation is used to simplify circuits where resistors are neither in series nor in parallel (e.g., a bridge circuit).
    *   A "Delta" (Δ) or "Pi" (Π) configuration of three resistors can be converted into an equivalent "Wye" (Y) or "Tee" (T) configuration.
    *   **Delta-to-Wye Conversion:**
        *   R1 = (Ra * Rc) / (Ra + Rb + Rc)
        *   R2 = (Ra * Rb) / (Ra + Rb + Rc)
        *   R3 = (Rb * Rc) / (Ra + Rb + Rc)
    *   **Wye-to-Delta Conversion:**
        *   Ra = (R1*R2 + R2*R3 + R3*R1) / R3
        *   Rb = (R1*R2 + R2*R3 + R3*R1) / R1
        *   Rc = (R1*R2 + R2*R3 + R3*R1) / R2

By applying these simplification techniques, a complex circuit can often be reduced to a form where methods like nodal analysis, mesh analysis, or the superposition theorem can be applied more easily.

## 8. Controlled Sources in Analysis

**Theory:**
Controlled (or dependent) sources are voltage or current sources whose values depend on a voltage or current elsewhere in the circuit. They are fundamental components in modeling active devices like transistors and operational amplifiers.

There are four types of controlled sources:
1.  **Voltage-Controlled Voltage Source (VCVS):** Output voltage is proportional to an input voltage (e.g., A * Vx).
2.  **Current-Controlled Voltage Source (CCVS):** Output voltage is proportional to an input current (e.g., r * Ix).
3.  **Voltage-Controlled Current Source (VCCS):** Output current is proportional to an input voltage (e.g., g * Vx).
4.  **Current-Controlled Current Source (CCCS):** Output current is proportional to an input current (e.g., β * Ix).

**Analysis with Controlled Sources:**
When applying nodal or mesh analysis to circuits with controlled sources:
*   Treat the controlled source like an independent source initially, but express its value in terms of the controlling voltage or current.
*   The controlling variable must be one of the node voltages (for VCVS, VCCS) or mesh currents (for CCVS, CCCS) that you are solving for, or it must be expressible in terms of them.
*   This will result in a system of equations where the controlled source terms are functions of other unknown variables, making the system coupled.
*   Solve the resulting system of linear equations to find all unknown voltages and currents.

## 9. Transient Analysis of First-Order Circuits

**Theory:**
Transient analysis deals with the behavior of circuits containing energy storage elements (capacitors and inductors) when there is a sudden change in the circuit, such as switching a voltage or current source on or off. First-order circuits contain only one energy storage element (either one capacitor or one inductor) and can be described by a first-order differential equation.

The general form of the solution for a first-order circuit variable (voltage or current) is:
x(t) = x_final + (x_initial - x_final) * e^(-t/τ)

Where:
*   x(t): The variable (voltage or current) at time t.
*   x_initial: The initial value of the variable just before the change (at t=0- or t=0+).
*   x_final: The final (steady-state) value of the variable as t approaches infinity.
*   τ (tau): The time constant of the circuit.

## 10. Natural and Step Response of RL Circuits

### Natural Response of an RL Circuit
**Theory:**
The natural response occurs when the circuit's independent sources are suddenly turned off, and the stored energy in the inductor is allowed to dissipate through the resistive part of the circuit.

Consider an inductor L initially storing energy, connected to a resistor R.
The differential equation is: L(di/dt) + Ri = 0
The solution for the current i(t) is:
i(t) = I_0 * e^(-t/τ) for t ≥ 0
Where:
*   I_0: Initial current in the inductor at t=0.
*   τ = L/R: The time constant for an RL circuit.

**Statement:**
> The natural response of an RL circuit is an exponential decay of the inductor current with a time constant τ = L/R.

### Step Response of an RL Circuit
**Theory:**
The step response occurs when a DC voltage source is suddenly applied to an RL circuit (e.g., by closing a switch).

Consider an inductor L and resistor R connected in series with a DC voltage source Vs.
The differential equation is: L(di/dt) + Ri = Vs
The solution for the current i(t) is:
i(t) = (Vs/R) + (I_0 - Vs/R) * e^(-t/τ) for t ≥ 0
If the inductor is initially uncharged (I_0 = 0), then:
i(t) = (Vs/R) * (1 - e^(-t/τ)) for t ≥ 0

The voltage across the inductor is:
v_L(t) = Vs * e^(-t/τ) for t ≥ 0 (assuming I_0 = 0)

**Statement:**
> The step response of an RL circuit describes how the inductor current rises exponentially from its initial value to a final steady-state value (Vs/R) with a time constant τ = L/R. The inductor voltage decays exponentially.

## 11. Natural and Step Response of RC Circuits

### Natural Response of an RC Circuit
**Theory:**
The natural response occurs when a charged capacitor is allowed to discharge through a resistor, with no independent sources connected.

Consider a capacitor C initially charged to V_0, connected to a resistor R.
The differential equation is: C(dv/dt) + v/R = 0
The solution for the capacitor voltage v(t) is:
v(t) = V_0 * e^(-t/τ) for t ≥ 0
Where:
*   V_0: Initial voltage across the capacitor at t=0.
*   τ = RC: The time constant for an RC circuit.

**Statement:**
> The natural response of an RC circuit is an exponential decay of the capacitor voltage with a time constant τ = RC.

### Step Response of an RC Circuit
**Theory:**
The step response occurs when a DC voltage source is suddenly applied to an RC circuit.

Consider a capacitor C and resistor R connected in series with a DC voltage source Vs.
The differential equation for the capacitor voltage is: C(dv/dt) + v/R = Vs/R
The solution for the capacitor voltage v(t) is:
v(t) = Vs + (V_0 - Vs) * e^(-t/τ) for t ≥ 0
If the capacitor is initially uncharged (V_0 = 0), then:
v(t) = Vs * (1 - e^(-t/τ)) for t ≥ 0

The current through the circuit is:
i(t) = (Vs/R) * e^(-t/τ) for t ≥ 0 (assuming V_0 = 0)

**Statement:**
> The step response of an RC circuit describes how the capacitor voltage rises exponentially from its initial value to a final steady-state value (Vs) with a time constant τ = RC. The circuit current decays exponentially.