# Abstract Models

### M-01: Memory-Optimal Computation
Concept of choosing bit-depth based on the physical limits of the system being modeled, rather than software defaults. 
*Logic:* Physical sensor precision (e.g., 12-bit ADC) should dictate the `dtype` (e.g., `int16` or `float32`), not `float64`.