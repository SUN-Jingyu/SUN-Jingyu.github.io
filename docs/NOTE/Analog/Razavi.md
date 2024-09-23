# Razavi 电子电路 1

> 该笔记用于记录学习 Razavi Electronics Circuits 1

## 信号的完成性和匹配 Signal Integrity and Matching 

> Why do we need to analysis input and output impedance in analog circuit?

* __Input Impedance__: The input impedance of a circuit determines *how much of the input signal is absorbed by the circuit*. If the input impedance is too low compared to the source impedance(源阻抗), a significant *portion of the signal will be lost*, leading to signal attenuation.

* __Output Impedance__: The output impedance affects *how the circuit drives a load (负载)*. If the ouput impedance is not well-matched to the load impedance, *signal reflection or losses can occur*, especially in *high-frequency application*.

* __Impdance Matching__: In many analog cirits, especially in RF and audio aplications, impedae matching is essential to ensure *maximum power transfer* and *mnimize reflections*.

## Thevenin equivalent 戴南维等式

> Alternative analysis  

1. Determine ```Vth``` s(Thevenin voltage):  
    * Remove the load resistor from the original circuit.
    * Calculate the open-circuit voltage across the terminals where the load was connected. This is ```Vth```.

2. Determine ```Rth``` (Thevenin resistance):
    * Remove all voltage sources (replace them with short circuits) and current sources (replace them with open circuits).
    * Calculate the equivalent resistance seen from the load terminals. This is ```Rth```. 

3. Rebuild the circuit:  
    * Once you have ```Vth``` and ```Rth```, you can draw the Thevenin equivalent circuit with ```Vth``` in series with ```Rth```, and the load resistor connected to them.

