# Transient Protection and Filtering Module

## Overview
The Transient Protection and Filtering Module is engineered to safeguard devices connected to a 12V supply. Initially designed for marine (yacht) systems, its robust protection features make it equally suitable for automotive and other 12V applications.

## Protection Summary

| Protection Type              | Specification                           |
|------------------------------|-----------------------------------------|
| Voltage Spike Suppression    | Up to 24.4V clamping @ 16.4A            |
| Reverse Polarity Protection  | Up to -40V VDS                          |
| Noise Filtering              | 1pF and 100nF ceramic capacitors        |
| Voltage Regulation           | 9.1V Zener protection                   |
| EMI Suppression              | 1uH inductor for output ripple smoothing|
| Output Voltage Smoothing     | 47uF electrolytic capacitor             |

## Component Functionalities

| Component              | Protection/Function                                       | Specification                                                   |
|------------------------|-----------------------------------------------------------|-----------------------------------------------------------------|
| SMAJ15CA-TP            | Transient Voltage Suppression (TVS)                       | Clamps voltage to 24.4V @ 16.4A during transient events         |
| Ceramic Capacitors     | Noise Filtering                                           | 50V rating; 1pF and 100nF for high and low frequency filtering  |
| MOSFET                 | Reverse Polarity Protection                               | VDS -40V; protects against damage from reverse polarity          |
| Zener Diode            | Voltage Regulation/Protection                             | 9.1V nominal; limits VGS to protect MOSFET gate                  |
| 100Ω Resistor          | Current Limitation for Zener Diode                        | Limits current through Zener to protect it and MOSFET gate      |
| 50V 1uF X7R Capacitor  | Decoupling and Noise Filtering at Output                  | Filters high frequency noise post-inductor                       |
| Inductor               | EMI Suppression and Smoothing of Output Ripple            | 1uH; reduces EMI and ripple                                     |
| Electrolytic Capacitor | Smoothing of Output Voltage                               | 47uF, 35V; provides bulk capacitance for low frequency filtering |

## Power Loss Summary

### Generic Formulas for Power Loss Calculations

1. **MOSFET Conduction Losses:** \(P_{MOSFET} = I^2 \cdot R_{DS(on)}\)
2. **Resistor Losses:** \(P_{Resistor} = \frac{V^2}{R}\)
3. **Inductor Copper Losses:** \(P_{Inductor} = I^2 \cdot R_{DCR}\)

Where:
- \(I\) is the current through the component,
- \(R_{DS(on)}\) is the on-state resistance of the MOSFET,
- \(V\) is the voltage across the resistor,
- \(R\) is the resistance of the resistor,
- \(R_{DCR}\) is the DC resistance of the inductor.

### Power Loss Calculations for Different Loads

Assuming a 12V nominal input, the losses for 200mA, 500mA, and 1.5A loads are as follows:

- **200mA Load:**
  - \(P_{MOSFET} = 0.2^2 \times 0.02 = 0.0008W\)
  - \(P_{Resistor} = \frac{9.1^2}{100} = 0.8281W\)
  - \(P_{Inductor} = 0.2^2 \times 0.008 = 0.00032W\)
  - **Total Losses:** Approximately 0.8292W

- **500mA Load:**
  - \(P_{MOSFET} = 0.5^2 \times 0.02 = 0.005W\)
  - \(P_{Resistor} = \frac{9.1^2}{100} = 0.8281W\)
  - \(P_{Inductor} = 0.5^2 \times 0.008 = 0.002W\)
  - **Total Losses:** Approximately 0.8351W

- **1.5A Load:**
  - \(P_{MOSFET} = 1.5^2 \times 0.02 = 0.045W\)
  - \(P_{Resistor} = \frac{9.1^2}{100} = 0.8281W\)
  - \(P_{Inductor} = 1.5^2 \times 0.008 = 0.018W\)
  - **Total Losses:** Approximately 0.8911W

### Summary of Power Losses

| Load Current | Total Power Loss (W) |
|--------------|-----------------------|
| 200mA        | 0.8292                |
| 500mA        | 0.8351                |
| 1.5A         | 0.8911                |

These calculations indicate the efficiency of the module across different operational scenarios, with minimal losses even at higher loads, ensuring reliability and durability for connected devices.

## Documentation

Comprehensive documentation, including an installation guide, technical data sheets, safety and compliance information, and warranty details, is available upon request. For further assistance, please contact our technical support team.

