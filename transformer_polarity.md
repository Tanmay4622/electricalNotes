# Transformer Polarity: Theory and Determination

## 1. Understanding Transformer Polarity

### What is Polarity?
In the context of a transformer, **polarity** refers to the relative directional relationship of the voltages in the primary and secondary windings. At any given instant, the voltage at one end of the primary winding will be positive relative to the other end. Polarity tells us which terminal on the secondary side is positive at that same instant.

### The Dot Convention
To represent polarity on a circuit diagram, we use the **dot convention**. A dot is placed on one terminal of the primary winding and one terminal of the secondary winding.
- **Rule:** If current enters the dotted terminal of the primary winding, the voltage at the dotted terminal of the secondary winding will be positive with respect to the other secondary terminal.
- In simpler terms, the voltages at the dotted terminals are **in phase** with each other.

### Why is Polarity Important?
Knowing the polarity is critical when connecting transformers together.
1.  **Parallel Operation:** If two transformers are to be connected in parallel to share a load, they **must** have the same polarity. Connecting transformers with opposing polarities in parallel creates a dead short circuit, leading to massive circulating currents that will destroy the transformers.
2.  **Three-Phase Banks:** When forming three-phase transformer banks using single-phase transformers (e.g., Y-Δ or Δ-Δ connections), correct polarity is essential for the phase relationships to be correct. Incorrect polarity will lead to incorrect output voltages and large circulating currents.

For a single transformer feeding a simple load, polarity is generally not critical. However, it is a fundamental property that must be known for any advanced application.

## 2. Experiment to Determine Polarity (AC Voltmeter Test)

This test determines whether a transformer has **additive** or **subtractive** polarity.

### Circuit Setup
1.  Identify the High Voltage (HV) and Low Voltage (LV) windings of the transformer. Let the HV terminals be `H1` and `H2`, and the LV terminals be `X1` and `X2`.
2.  Connect a jumper wire between one terminal of the HV winding and the adjacent terminal on the LV winding (e.g., connect `H1` and `X1`).
3.  Apply a known AC voltage (`V_in`) across the HV winding (`H1` and `H2`) using a variac for safety.
4.  Using an AC voltmeter, measure the voltage across the two unconnected terminals (i.e., between `H2` and `X2`). Let's call this `V_out`.

### Procedure and Analysis
1.  Apply a safe voltage `V_in` to the HV winding.
2.  Measure the induced voltage across the LV winding to confirm the transformer's ratio.
3.  Measure the voltage `V_out` across the non-jumpered terminals (`H2` and `X2`).
4.  Compare `V_out` with the input voltage `V_in`.

- **Case 1: Subtractive Polarity**
  - If **`V_out < V_in`**, the transformer has subtractive polarity. This means the voltage in the secondary winding opposes the primary voltage in the series loop created by the jumper. `V_out` will be equal to the difference between the HV and LV winding voltages.
  - **Conclusion:** The connected terminals (`H1` and `X1`) have the same polarity. The dots are on `H1` and `X1`.

- **Case 2: Additive Polarity**
  - If **`V_out > V_in`**, the transformer has additive polarity. This means the secondary voltage aids the primary voltage in the series loop. `V_out` will be equal to the sum of the HV and LV winding voltages.
  - **Conclusion:** The connected terminals (`H1` and `X1`) have opposite polarity. The dots are on `H1` and `X2` (or `H2` and `X1`).

## 3. Viva Voce Questions

1.  **What do you understand by the term 'transformer polarity'?**
    *   It describes the instantaneous direction of the voltage in the secondary winding relative to the primary winding.

2.  **What is the purpose of the dot convention?**
    *   It is a shorthand notation on a circuit diagram to indicate which terminals of the primary and secondary windings have the same polarity (i.e., are in phase).

3.  **Why is it crucial to know the polarity of a transformer?**
    *   It is essential for connecting transformers in parallel or in three-phase banks. Incorrect polarity will cause a short circuit.

4.  **Describe the test you would perform to find a transformer's polarity.**
    *   Explain the AC voltmeter test: Jumper an HV and LV terminal, apply voltage to the HV side, and measure the voltage across the non-jumpered terminals.

5.  **In a polarity test, the input voltage is 120V and the voltage across the open terminals is 144V. What can you conclude?**
    *   Since the output measurement is greater than the input, the transformer has **additive polarity**.

6.  **What would happen if you connected two transformers with the same voltage rating but opposite polarity in parallel?**
    *   A very large circulating current would flow between the transformers, effectively creating a short circuit that would damage or destroy them. The secondary voltages would oppose each other instead of adding to supply the load.

7.  **For a standard power distribution transformer, would you expect it to have additive or subtractive polarity? Why?**
    *   Subtractive polarity is standard for larger distribution transformers. It's a safety feature. With subtractive polarity, the voltage between adjacent HV and LV terminals is lower, reducing the risk of insulation breakdown and flashover. Additive polarity is more common in small instrument transformers.