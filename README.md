# NGCs Framework – Source Data

This repository contains the source data for the paper:

**"A NGCs framework for glass structure–property prediction and rational composition design"**  
Authors: Minbo Wu, Guowu Tang, Xiangyang Song, et al.

---

## Repository Structure


---

## Folder Description

| Folder | Content | Format |
|--------|---------|--------|
| `01_Experimental_Data` | Compiled experimental dataset of over 10,000 glass compositions with measured properties and structural species, collected from cited references and the SciGlass database. | Excel (`.xlsx`) |
| `02_Figure_4_Quaternary_Plots` | Source data for Figure 4: quaternary plots of sodium calcium aluminosilicate glasses showing predicted density, refractive index, and glass transition temperature. | Excel (`.xlsx`) |
| `03_Figure_5_Composition_Series` | Source data for Figure 5: composition–property relationships in Na₂O–B₂O₃–SiO₂ glasses, including predicted [BO₄] fractions and measured mechanical properties. | Excel (`.xlsx`) |
| `04_Figure_6_Multi_Property_Optimization` | Source data for Figure 6: glass selection charts for the 7‑component Na₂O–K₂O–CaO–MgO–Al₂O₃–B₂O₃–SiO₂ system. Due to large dataset size, data are stored in Python pickle format. | Python pickle (`.pkl`) |

---

## File Details

### 01_Experimental_Data

This folder contains the compiled experimental dataset organized by property and structural species. Each Excel file corresponds to one property or structural species and includes composition data and measured values collected from literature and the SciGlass database.

| File Name | Content | Description |
|-----------|---------|-------------|
| `[BO4] data.xlsx` | [BO₄] fraction | Fraction of four-coordinated boron in borate-containing glasses |
| `Abbe number.xlsx` | Abbe number (V<sub>d</sub>) | Dimensionless measure of optical dispersion |
| `Density.xlsx` | Density (D) | Mass density in g/cm³ |
| `Glass transition temperature.xlsx` | Glass transition temperature (T<sub>g</sub>) | In °C |
| `Pn_data.xlsx` | Qⁿ(P) speciation | Connectivity of phosphorus-oxygen tetrahedra in phosphate glasses |
| `Refractive index.xlsx` | Refractive index (n<sub>d</sub>) | At sodium D line |
| `Sn_data.xlsx` | Qⁿ(Si) speciation | Connectivity of silicon-oxygen tetrahedra in silicate glasses |
| `Thermal expansion coefficient.xlsx` | Thermal expansion coefficient (α) | In 10⁻⁷ K⁻¹ |
| `Young's modulus.xlsx` | Young's modulus (E) | In GPa |

**Note**: Each file contains columns for glass composition (oxide components such as Na₂O, CaO, SiO₂, B₂O₃, etc.) and the corresponding measured value. See individual files for detailed column headers and units.

---

### 02_Figure_4_Quaternary_Plots

This folder contains the source data for Figure 4: quaternary plots of sodium calcium aluminosilicate glasses. Each Excel file corresponds to one predicted property across the quaternary composition space (Na₂O–CaO–Al₂O₃–SiO₂).

| File Name | Property | Description |
|-----------|----------|-------------|
| `Density.xlsx` | Density (D) | Predicted density values in g/cm³ |
| `Glass transition temperature.xlsx` | Glass transition temperature (T<sub>g</sub>) | Predicted Tg values in °C |
| `Refractive index.xlsx` | Refractive index (n<sub>d</sub>) | Predicted refractive index values at sodium D line |

**Note**: Each file contains columns for composition (Na₂O, CaO, Al₂O₃, SiO₂) and the corresponding predicted property value. The composition points cover the ranges shown in Figure 4 with constraints (x+y+z)≤1, and subsets with x,y,z∈[0.3,1] and x,y,z∈[0.5,1].

---

### 03_Figure_5_Composition_Series

This folder contains the source data for Figure 5: composition–property relationships in Na₂O–B₂O₃–SiO₂ glasses.

| File Name | Content | Description |
|-----------|---------|-------------|
| `generate_[BO4].xlsx` | Predicted [BO₄] fractions | Generated [BO₄] values as functions of B₂O₃ concentration for the glass series 10Na₂O–xB₂O₃–(90-x)SiO₂ and 20Na₂O–yB₂O₃–(90-y)SiO₂ |
| `measure_D_E.xlsx` | Measured density and Young's modulus | Experimental values of density (D) and Young's modulus (E) for the same glass series, used in Figure 5a,b and Figure 5d-f |

**Note**: 
- `generate_[BO4].xlsx` contains the predicted [BO₄] fractions corresponding to Figure 5c.
- `measure_D_E.xlsx` contains the experimental density and Young's modulus values used in Figure 5a,b and the relationships with [BO₄] shown in Figure 5d-f.

---

### 04_Figure_6_Multi_Property_Optimization

This folder contains the source data for Figure 6: glass selection charts for the 7‑component Na₂O–K₂O–CaO–MgO–Al₂O₃–B₂O₃–SiO₂ system. Due to the large number of compositions (26,334 unique glass compositions), the data are stored in Python pickle format.

| File Name | Property | Unit |
|-----------|----------|------|
| `results_D.pkl` | Density (D) | g/cm³ |
| `results_E.pkl` | Young's modulus (E) | GPa |
| `results_nd.pkl` | Refractive index (n<sub>d</sub>) | – (dimensionless) |
| `results_Tg.pkl` | Glass transition temperature (T<sub>g</sub>) | °C |
| `results_Vd.pkl` | Abbe number (V<sub>d</sub>) | – (dimensionless) |
| `results_α.pkl` | Thermal expansion coefficient (α) | 10⁻⁷ K⁻¹ |

**Important**: 
- The order of values in every `.pkl` file is identical and follows the nested‑loop order used to generate the composition grid (see the folder's README for details).
- See `04_Figure_6_Multi_Property_Optimization/README.md` for detailed instructions on how to read these files and regenerate the composition coordinates.

---

## Data Availability Statement

The data that support the findings of this study are available from the cited references and the SciGlass database (https://github.com/epam/SciGlass). The compiled experimental dataset and the predicted values for Figures 4–6 are provided in this GitHub repository. A summary of the compiled dataset is available in Supplementary Table 1 of the paper.

---

## How to Cite

If you use this data in your research, please cite the original paper:

[Citation information to be added upon publication]

---

## Contact

For questions about the data or the NGCs framework, please contact the corresponding author.
