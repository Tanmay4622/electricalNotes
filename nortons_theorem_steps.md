# Steps for Applying Norton's Theorem:

1.  **Remove the load resistor (R_L):** Identify the load resistor across which you want to find the current and remove it from the circuit.
2.  **Find the Norton current (I_N):**
    *   Short-circuit the terminals from which the load resistor was removed.
    *   Calculate the current flowing through this short circuit. This is the Norton current (I_N). Use techniques like mesh analysis, nodal analysis, or superposition.
3.  **Find the Norton resistance (R_N):**
    *   Deactivate all independent sources in the original circuit (voltage sources become short circuits, current sources become open circuits).
    *   If there are dependent sources, they must remain active. In this case, you might need to apply a test voltage (V_T) or test current (I_T) source across the open-circuited terminals and find the ratio R_N = V_T / I_T.
    *   Calculate the equivalent resistance looking back into the terminals where the load resistor was removed. This is the Norton resistance (R_N).
4.  **Draw the Norton equivalent circuit:** The Norton equivalent circuit consists of a Norton current source (I_N) in parallel with the Norton resistance (R_N).
5.  **Reconnect the load resistor (R_L):** Place the original load resistor (R_L) back across the terminals of the Norton equivalent circuit.
6.  **Calculate the current through R_L:** Use the current divider rule to find the current flowing through the load resistor (I_L) in the Norton equivalent circuit:
    I_L = I_N * (R_N / (R_N + R_L))

---

## Common Questions for a Viva

### Why do we short the terminals where the load was?

We short the terminals for a specific reason: **to find the Norton Current (I_N)**.

The Norton Current is defined as the **maximum possible current** that the original linear circuit can deliver from its two output terminals. According to Ohm's Law (I = V/R), for any given voltage supplied by the circuit, the maximum current is achieved when the resistance across the terminals is the absolute minimum, which is zero. A short circuit provides a path of zero resistance.

By placing a short circuit across the terminals, we create the exact condition needed to calculate this maximum current, which, by definition, is the Norton Current (I_N) for the equivalent circuit.

### What is the relationship between Norton's theorem and Thevenin's theorem?

They are **duals** of each other and are interchangeable through source transformation. 
- A Thevenin equivalent circuit is a voltage source (V_Th) in **series** with a resistor (R_Th).
- A Norton equivalent circuit is a current source (I_N) in **parallel** with a resistor (R_N).

The relationship is:
- The resistances are identical: `R_N = R_Th`
- The Norton current is the short-circuit current, which can be found from the Thevenin circuit: `I_N = V_Th / R_Th`

### To what kind of circuits does Norton's theorem apply?

Norton's theorem is only applicable to **linear, bilateral networks**.
- **Linear:** The relationship between voltage and current is linear (i.e., it follows Ohm's law). The circuit's parameters (like resistance) do not change with voltage or current.
- **Bilateral:** The circuit's properties and characteristics are the same regardless of the direction of current flow.

### How do you find the Norton Resistance (R_N) if the circuit has dependent sources?

When a circuit contains dependent sources, you cannot simply deactivate them like independent sources. Instead, you must:
1. Deactivate all **independent** sources (voltage sources become shorts, current sources become opens).
2. Apply a known **test voltage (V_T)** across the output terminals and measure the resulting **test current (I_T)**.
3. Calculate the Norton resistance using Ohm's Law: `R_N = V_T / I_T`.

### What is the main advantage of using Norton's Theorem?

The primary advantage is **simplification**. It allows you to replace a large, complex part of a circuit with a very simple equivalent current source and parallel resistor. This is extremely useful when you need to perform calculations for a **variable load**. Instead of re-analyzing the entire complex circuit every time the load changes, you can use the simple Norton equivalent and quickly calculate the load current or voltage.