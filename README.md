# Dynamical Mass of a Galaxy Cluster – Project Report

---

## 1. What is This Project About?

This project focuses on the determination of the **dynamical mass** of a galaxy cluster using computational methods, specifically employing **Python** and the **Astropy** library. By analyzing observational data of galaxies within a cluster, we aim to calculate its total mass based on the motion of its constituent galaxies.

---

## 2. What Does Dynamical Mass Even Mean?

The **dynamical mass** of a galaxy cluster refers to the total mass inferred from the gravitational influence it exerts on the motion of its member galaxies. Unlike **luminous mass** (derived from emitted light), dynamical mass includes **all matter**, notably **dark matter**, which interacts only gravitationally.

It is typically calculated by:

- Observing galaxy velocities within a cluster.
- Applying gravitational principles (e.g., the **virial theorem**).

---

## 3. How Is It Important in the Field of Astronomy?

Dynamical mass is important because it helps:

- **Understand Dark Matter:** Discrepancies between luminous and dynamical mass indicate the presence of dark matter.
- **Study Cluster Evolution:** The total mass affects cluster formation and interactions.
- **Constrain Cosmological Parameters:** Useful for understanding the matter density of the universe and the nature of dark energy.

---

## 4. Applications of the Dynamical Mass of a Cluster

- **Mapping Dark Matter Distribution**
- **Testing Cosmological Models**
- **Studying Galaxy Formation**
- **Cross-validating with Gravitational Lensing**

---

## 5. Explanation of Other Relevant Terms

| Term                    | Description |
|-------------------------|-------------|
| **Redshift (z)**        | Spectral shift indicating a galaxy's velocity and distance. |
| **Velocity Dispersion (σ)** | Spread in velocities of galaxies in a cluster. |
| **Angular Diameter Distance (DA)** | Converts angular size to physical distance. |
| **Co-moving Distance (rₘ)** | Distance unaffected by universe expansion. |
| **Virial Theorem**      | \( 2T + U = 0 \), relates kinetic and potential energy for bound systems. |

---

## 6. Tools Used

| Tool       | Purpose |
|------------|---------|
| **Python** | Programming language used for computation. |
| **Astropy** | Provides constants, units, and cosmology tools. |
| **Pandas** | Data ingestion and preprocessing. |
| **NumPy** | Numerical and statistical operations. |
| **Matplotlib** | Data visualization. |

---

## 7. Theoretical Framework & Procedure

### Virial Theorem Equation:
\[
M_{\text{dyn}} = \frac{3 \cdot \sigma^2 \cdot R}{G}
\]

Where:
- \( \sigma \): Velocity dispersion
- \( R \): Radius
- \( G \): Gravitational constant

### Velocity Calculation (Relativistic Doppler):
\[
v_{\text{rel}} = c \cdot \frac{(1+z_{\text{gal}})^2 - (1+z_{\text{cluster}})^2}{(1+z_{\text{gal}})^2 + (1+z_{\text{cluster}})^2}
\]

---

### Procedure

1. **Data Ingestion**: Load data using `pandas.read_csv`.
2. **Preprocessing**:
   - Average redshifts per `objid`.
   - Clean missing values.
3. **Redshift-based Filtering**:
   - Apply 3σ cut-off to isolate cluster members.
   - Visualize with boxplots/histograms.
4. **Velocity Calculation**:
   - Convert redshift to velocity.
   - Compute relative velocities.
5. **Velocity Dispersion**:
   - Use standard deviation of velocities.
6. **Cluster Radius Estimation**:
   - Calculate co-moving and angular diameter distances.
   - Convert angular separation to physical radius.
7. **Dynamical Mass Calculation**:
   - Apply virial theorem.
   - Convert mass to solar masses.
8. **Visualization**:
   - Plot redshift, velocity, separation histograms.

---

## 8. Implementation Details

### 1. Import Libraries

```python
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd
from astropy.constants import G, c
from astropy.cosmology import Planck18 as cosmo
import astropy.units as u
```

### 2. Define Constants

```python
H_0 = (67.4 * u.km / u.s / u.Mpc).to(1/u.s)
q0 = -0.534
```

### 3. Read Data

```python
file_name = r"C:\Users\haric\Documents\..."
df = pd.read_csv(file_name, header=1)
```

### 4–11. Core Steps: Averaging, Filtering, Velocity, Mass Calculation (as explained above)

---

## 9. Results & Discussion

### Defined Constants

| Constant         | Value |
|------------------|-------|
| \( H_0 \)        | 2.18 × 10⁻¹⁸ s⁻¹ |
| \( c \)          | 299,792,458 m/s |
| \( G \)          | 6.6743 × 10⁻¹¹ m³/kg/s² |
| \( q_0 \)        | −0.534 |

### Redshift Analysis

- Mean redshift: **0.0989**
- Std deviation: **0.0101**
- 3σ cut reduced dataset from 100 to 99 galaxies.

### Velocity Dispersion

- Cluster redshift: **0.0985**
- \( \sigma \): **2565.34 km/s**
- Velocity range: **±6000 km/s**

### Cluster Size

- Co-moving distance: **428.2 Mpc**
- Angular diameter distance: **389.8 Mpc**
- Physical diameter: **1.12 Mpc**

### Dynamical Mass

- Mass: **≈ 2.55 × 10¹⁵ M☉**
- Indicates large cluster and significant **dark matter** presence.

---

## 10. Conclusion

This project successfully demonstrates the use of **computational astrophysics** to estimate the **dynamical mass** of a galaxy cluster using real data and Python libraries. The high mass confirms dark matter's influence and reinforces the power of spectroscopic analysis in modern astronomy. The methods here are scalable to larger datasets for more complex studies.

---

## 11. References

- **ISA Summer School Materials**
- **GitHub Repository**: [ISA-Summer_School_2025](https://github.com/supremeKAI40/ISA-Summer_School_2025)  
- **Project Handout**: [Dynamical Mass Project PDF](https://github.com/supremeKAI40/ISA-Summer_School_2025/blob/main/projects/dynamical_mass/1_Cluster-Dynamical-Cluster_handout.pdf)
