# SIWDES Model Quick Reference Guide

## Xiang et al. (2013) Six-Region Mechanistic Framework

### Model Name: SIWDES
**S**upercritical CO2 - **I**nterface - **W**ater film - **D**eposition - **E**lectrodic - **S**olid

*Note: The acronym contains two 'S' regions - the first for Supercritical CO2 (bulk fluid) and the last for Solid steel substrate. These represent the two boundaries of the corrosion system.*

---

## Region Descriptions

### Region 1: Supercritical CO2 (S)
**Physical State:** Supercritical fluid (T > 31.1°C, P > 7.38 MPa)

**Key Processes:**
- Bulk transport of impurities (SO2, O2, H2O)
- Diffusion toward steel surface
- Phase equilibria with aqueous film

**Governing Equations:**
- Mass transport in supercritical phase
- Gas-liquid solubility (Henry's Law modified for scCO2)

**Important Parameters:**
- Diffusion coefficients in scCO2
- Solubility of gases in supercritical phase
- Bulk concentrations of impurities

---

### Region 2: Interface (I)
**Physical State:** Gas-liquid boundary

**Key Processes:**
- Phase transfer of CO2, SO2, O2 into water film
- Equilibrium partitioning between phases
- Mass transfer resistance

**Governing Equations:**
- Phase equilibrium: K_H = C_liquid / C_gas
- Interfacial mass balance

**Important Parameters:**
- Henry's constants for each species
- Temperature and pressure dependence
- Interfacial area

---

### Region 3: Water Film (W)
**Physical State:** Thin aqueous electrolyte layer on steel surface

**Key Processes:**
- CO2 hydration: CO2 + H2O ⇌ H2CO3
- Acid dissociation:
  - H2CO3 ⇌ H+ + HCO3- (pKa1 ~ 6.4)
  - HCO3- ⇌ H+ + CO3²- (pKa2 ~ 10.3)
- SO2 reactions:
  - SO2 + H2O → H2SO3
  - H2SO3 → H+ + HSO3-
  - HSO3- → H+ + SO3²-
  - Oxidation: H2SO3 + ½O2 → H2SO4
- Ion transport to/from steel surface
- pH buffering

**Governing Equations:**
- Diffusion: ∂C/∂t = D * ∂²C/∂x²
- Chemical equilibria (mass action)
- Electroneutrality: Σ(z_i * C_i) = 0
- Activity coefficients (modified 3-parameter model)

**Important Parameters:**
- Film thickness (typically 10-100 μm)
- Diffusion coefficients in water
- Equilibrium constants (temperature dependent)
- Ionic strength (very high in thin films)
- pH at steel surface (critical for corrosion rate)

---

### Region 4: Deposition (D)
**Physical State:** Solid corrosion product layer

**Key Processes:**
- Precipitation of iron carbonate:
  - Fe²+ + CO3²- → FeCO3(s)
- Precipitation of iron sulfate/sulfite species
- Product layer growth or dissolution
- Mass transport through porous layer

**Governing Equations:**
- Precipitation/dissolution kinetics
- Diffusion through porous layer
- Film thickness evolution
- Protective vs non-protective film criteria

**Important Parameters:**
- FeCO3 solubility product (Ksp ~ 10^-11)
- Layer thickness
- Porosity and tortuosity
- Adhesion to steel surface
- Protective efficiency

---

### Region 5: Electrodic (E)
**Physical State:** Electrochemical double layer at steel surface

**Key Processes:**

**Anodic Reaction (oxidation):**
```
Fe → Fe²+ + 2e-
```

**Cathodic Reactions (reduction):**
```
2H+ + 2e- → H2         (hydrogen evolution)
O2 + 4H+ + 4e- → 2H2O  (oxygen reduction, if O2 present)
H2CO3 + 2e- → ...      (direct reduction, minor)
```

**Governing Equations:**
- Butler-Volmer equation:
  ```
  i = i0 * [exp(αa*F*η/RT) - exp(-αc*F*η/RT)]
  ```
- Mixed potential theory (E_corr where i_anodic = i_cathodic)
- Tafel approximation at high overpotentials
- Faraday's law for corrosion rate:
  ```
  CR (mm/year) = 0.00327 * i_corr * M / (n * ρ)
  ```

**Important Parameters:**
- Exchange current density (i0)
- Transfer coefficients (αa, αc typically ~ 0.5)
- Tafel slopes (ba, bc)
- Corrosion potential (E_corr)
- Corrosion current density (i_corr)
- pH at steel surface

---

### Region 6: Solid Steel (S)
**Physical State:** Metal substrate

**Key Processes:**
- Electron conduction
- Iron dissolution at surface
- Substrate degradation (metal loss)

**Governing Equations:**
- Ohm's law for electron transport
- Mass balance for metal loss

**Important Parameters:**
- Steel composition (C, Mn, Si, etc.)
- Electrical conductivity
- Density (ρ ~ 7.85 g/cm³ for carbon steel)
- Molar mass (M ~ 55.85 g/mol for Fe)

---

## Coupled System Solution

### Integration Strategy

The six regions are **coupled** through:
1. **Mass balances** at interfaces
2. **Charge conservation** (electroneutrality)
3. **Thermodynamic equilibria**
4. **Electrochemical mixed potential**

### Solution Approach

1. **Initial Guess:**
   - Assume initial pH, concentrations, E_corr
   
2. **Iterative Solution:**
   - Solve mass transport in each region
   - Calculate concentrations at interfaces
   - Determine pH and ionic strength
   - Calculate activity coefficients
   - Solve electrochemical equations for i_corr
   - Update concentrations and repeat
   
3. **Convergence:**
   - Iterate until mass balances satisfied
   - Check charge neutrality
   - Verify electrochemical consistency

4. **Output:**
   - Corrosion rate (mm/year)
   - Concentration profiles
   - pH profile
   - Product layer thickness

---

## Critical Parameters for Corrosion Rate

### Environmental Conditions
- **Temperature:** Affects kinetics, equilibria, solubilities
- **Pressure:** Determines scCO2 properties, gas solubilities
- **pCO2:** Partial pressure of CO2
- **pSO2:** Partial pressure of SO2 (ppm level)
- **pO2:** Partial pressure of O2 (ppm level)
- **pH2O:** Partial pressure/content of water

### Electrochemical Parameters
- **pH at steel surface:** Most critical parameter
  - Low pH → high corrosion rate
  - SO2 drastically lowers pH
- **i0 (exchange current density):** Steel-specific
- **Tafel slopes:** Reaction mechanisms

### Transport Properties
- **Diffusion coefficients:**
  - In scCO2: ~10^-8 to 10^-7 m²/s
  - In water: ~10^-9 m²/s
- **Water film thickness:** 10-100 μm typical

### Product Layer Properties
- **FeCO3 supersaturation:** Determines precipitation
- **Layer porosity:** Affects protectiveness
- **Adhesion:** Critical for long-term protection

---

## Impurity Effects Summary

### SO2 Impact
- **Mechanism:**
  - Forms H2SO3/H2SO4 in water film
  - Drastically lowers pH (pH < 3 possible)
  - Increases H+ concentration → accelerates cathodic reaction
- **Effect:** 10-100x increase in corrosion rate

### O2 Impact
- **Mechanism:**
  - Additional cathodic depolarizer
  - Reduces hydrogen overpotential
  - Oxidizes SO2 to more acidic forms
- **Effect:** 5-50x increase in corrosion rate

### H2O Impact
- **Mechanism:**
  - Essential for aqueous corrosion
  - No corrosion in dry scCO2
  - Film thickness increases with water content
- **Critical Threshold:** ~500 ppm (depends on T, P)

### Synergistic Effect
- **SO2 + O2 + H2O:** Multiplicative effect
- **Total Enhancement:** 100-1000x compared to pure CO2

---

## Model Applications

### Design Calculations
1. **Maximum allowable impurity levels**
   - Set target corrosion rate (e.g., <0.1 mm/year)
   - Calculate maximum [SO2], [O2], [H2O]

2. **Pipeline lifetime prediction**
   - Input: operating conditions, wall thickness
   - Output: time to reach minimum wall thickness

3. **Material selection**
   - Compare different steel grades
   - Evaluate cost vs. corrosion resistance

### Operational Monitoring
1. **Real-time predictions**
   - Update model with measured impurity levels
   - Predict current corrosion rate

2. **Alarm thresholds**
   - Set limits on impurities based on acceptable corrosion

### Mitigation Strategies
1. **Dehydration requirements**
   - Calculate maximum water content
   
2. **Purification needs**
   - SO2 removal specifications
   - O2 removal specifications

3. **Inhibitor evaluation**
   - Model effect of corrosion inhibitors on i_corr

---

## Typical Input Values

### CCS Pipeline Conditions
- **Temperature:** 25-50°C
- **Pressure:** 10-20 MPa (supercritical)
- **CO2 purity:** >95%
- **SO2:** <100 ppm (target < 10 ppm)
- **O2:** <100 ppm (target < 10 ppm)
- **H2O:** <500 ppm (target < 50 ppm)

### Steel Properties (API 5L X65)
- **Composition:** ~0.15% C, balance Fe
- **Density:** 7.85 g/cm³
- **Typical wall thickness:** 10-20 mm

---

## Typical Output Values

### Corrosion Rates
- **Pure CO2 + H2O:** 0.01-0.1 mm/year
- **CO2 + H2O + SO2 (10 ppm):** 0.1-1 mm/year
- **CO2 + H2O + SO2 + O2:** 1-10 mm/year
- **High impurities:** >10 mm/year (unacceptable)

### Design Criteria
- **Acceptable:** <0.1 mm/year (design life 20-50 years)
- **Marginal:** 0.1-0.5 mm/year (shorter life, monitoring required)
- **Unacceptable:** >0.5 mm/year (purification or alternative materials needed)

---

## Key Equations Summary

### 1. Corrosion Rate from Current Density
```
CR (mm/year) = 0.00327 * i_corr * M / (n * ρ)
```
Where:
- i_corr = corrosion current density (μA/cm²)
- M = atomic weight (55.85 g/mol for Fe)
- n = number of electrons (2 for Fe → Fe²+)
- ρ = density (7.85 g/cm³)

### 2. Butler-Volmer Equation
```
i = i0 * [exp(αa*n*F*η/RT) - exp(-αc*n*F*η/RT)]
```

### 3. Tafel Equation (high overpotential)
```
η = ba * log(i/i0)  [anodic]
η = -bc * log(i/i0) [cathodic]
```

### 4. Mixed Potential Condition
```
i_anodic = i_cathodic  (at E_corr)
```

### 5. Activity Coefficient (simplified)
```
log(γ) = -A * z² * √I / (1 + B * a * √I) + C * I
```

---

*Quick reference for model implementation and application*  
*See full paper summary for detailed explanations*
