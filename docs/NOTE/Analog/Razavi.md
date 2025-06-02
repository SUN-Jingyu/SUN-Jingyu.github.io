# Razavi 电子电路 1

> 该笔记用于记录学习 Razavi Electronics Circuits 1

## 信号的完成性和匹配 Signal Integrity and Matching

> Why do we need to analysis input and output impedance in analog circuit?

* __Input Impedance__: The input impedance of a circuit determines *how much of the input signal is absorbed by the circuit*. If the input impedance is too low compared to the source impedance(源阻抗), a significant *portion of the signal will be lost*, leading to signal attenuation.

* __Output Impedance__: The output impedance affects *how the circuit drives a load (负载)*. If the ouput impedance is not well-matched to the load impedance, *signal reflection or losses can occur*, especially in *high-frequency application*.

* __Impdance Matching__: In many analog cirits, especially in RF and audio aplications, impedae matching is essential to ensure *maximum power transfer* and *mnimize reflections*.

## Thevenin equivalent 戴南维等式

> Alternative analysis  

1. Determine ```Vth``` (Thevenin voltage):  
    * Remove the load resistor from the original circuit.
    * Calculate the open-circuit voltage across the terminals where the load was connected. This is ```Vth```.

2. Determine ```Rth``` (Thevenin resistance):
    * Remove all voltage sources (replace them with short circuits) and current sources (replace them with open circuits).
    * Calculate the equivalent resistance seen from the load terminals. This is ```Rth```.

3. Rebuild the circuit:  
    * Once you have ```Vth``` and ```Rth```, you can draw the Thevenin equivalent circuit with ```Vth``` in series with ```Rth```, and the load resistor connected to them.

## 退化电阻对于共射极(BJT)和共源极(MOSFET)的影响

### 无退化电阻时的增益推导

1. 共射极放大器BJT (CE without $R_E$):
    * Without Early effect:
        $$
            A_v = -g_m R_C
        $$
    * With Early effect:
        $$
            A_v = -g_m \left(R_C \parallel r_o\right)
        $$

2. 共源极放大器MOSFET (CS without $R_S):
    * Without Channel Length Modulation:
        $$
            A_v = -g_m R_D
        $$
    * With Channel Length Modulation:
        $$ A_v = -g_m (R_D \parallel r_o) $$

### 有退化电阻时的增益推导

1. 共射极放大器BJT (CE with $R_E$):
    * Without Early effect:
        $$
            A_v = -\frac{g_m R_C}{1 + g_m R_E}
        $$
    * With Early effect:
        $$
            A_v = -\frac{g_m (R_C \parallel r_o)}{1 + g_m R_E}
        $$

2. 共源极放大器MOSFET (CS with $R_S):
    * Without Channel Length Modulation:
        $$
             A_v = -\frac{g_m R_D}{1 + g_m R_S}
        $$
    * With Channel Length Modulation:
        $$ A_v = -\frac{g_m (R_D \parallel r_o)}{1 + g_m R_S} $$

> These expressions often __ignore $r_o$__ (output resistance), and here's why.

---

### Why Is $r_o$ Often Ignored with Degeneration?

#### Reasons

1. __Degeneration introduces local feedback__, increasing output impedance and reducing the influence of $r_o$.

2. __Simplifies design and teaching__ — textbooks often omit second-order effects in first-pass analysis.

3. __r_o is typically large__, making its impact negligible in many practical cases:
   * BJT: $$ r_o = \frac{V_A}{I_C} $$
   * MOSFET: $$ r_o = \frac{1}{\lambda I_D} $$

忽略 $r_o$ 是一种建模简化，适用于初步分析和大多数设计情况。对于高精度设计、宽带电路或高阻负载时，必须考虑 $r_o$（Early effect 或 Channel Length Modulation） 的影响。
