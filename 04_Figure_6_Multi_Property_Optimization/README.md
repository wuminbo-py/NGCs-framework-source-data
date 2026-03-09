# Figure 6 Source Data – Multi-Property Optimization

This folder contains the source data for **Figure 6** in the manuscript:

**Figure 6** | Generating glass selection charts of the Na₂O–K₂O–CaO–MgO–Al₂O₃–B₂O₃–SiO₂ system for multi-property optimization.

---

## File Overview

Due to the large number of glass compositions evaluated, the data are stored in **Python pickle (`.pkl`)** format.  
Each file contains the predicted values for one specific property across **all composition points** used to generate Figure 6.

| File Name       | Property                          | Unit (as used in the paper) |
|-----------------|-----------------------------------|-----------------------------|
| `results_D.pkl` | Density (D)                       | g/cm³                       |
| `results_E.pkl` | Young’s modulus (E)               | GPa                         |
| `results_nd.pkl`| Refractive index (n<sub>d</sub>)  | – (dimensionless)           |
| `results_Tg.pkl`| Glass transition temperature (T<sub>g</sub>) | °C                     |
| `results_Vd.pkl`| Abbe number (V<sub>d</sub>)       | – (dimensionless)           |
| `results_α.pkl` | Thermal expansion coefficient (α) | 10⁻⁷ K⁻¹                    |

---

## Composition Grid

The predicted values correspond to a **systematically generated composition grid** in the 7‑component oxide space:

- **Components**: Na₂O, K₂O, CaO, MgO, Al₂O₃, B₂O₃, SiO₂  
- **Concentration range for each modifier (Na₂O … B₂O₃)**: 0 – 50 mol%  
- **Step size**: 2 mol%  
- **SiO₂ content**: calculated as `SiO₂ = 100 – (Na₂O + K₂O + CaO + MgO + Al₂O₃ + B₂O₃)`  
- **Constraint**: Only compositions with `SiO₂ ≥ 50 mol%` are included.

This results in a total of **26,334 unique glass compositions**, which is the exact number used to construct the selection charts in Figure 6.

**Important:**  
The **order of values** in every `.pkl` file is **identical** and follows the nested‑loop order used to generate the composition grid:

```python
for c_Na2O in range(0, 51, 2):
    for c_K2O in range(0, 51, 2):
        for c_CaO in range(0, 51, 2):
            for c_MgO in range(0, 51, 2):
                for c_Al2O3 in range(0, 51, 2):
                    for c_B2O3 in range(0, 51, 2):
                        c_SiO2 = 100 - c_Na2O - c_K2O - c_CaO - c_MgO - c_Al2O3 - c_B2O3
                        if c_SiO2 >= 50:
                            # store composition