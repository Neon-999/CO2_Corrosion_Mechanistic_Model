# Documentation - CO2 Corrosion Mechanistic Model

This directory contains research papers and documentation related to mechanistic models for CO2 corrosion in pipeline steels, with a focus on Carbon Capture and Storage (CCS) applications.

## Contents

### Research Papers

The following research papers provide the theoretical foundation for this project:

1. **Xiang et al. (2013)** - *A mechanistic model for pipeline steel corrosion in supercritical CO2–SO2–O2–H2O environments*
   - Primary reference for this project
   - Detailed summary available: [Xiang_2013_Paper_Summary.md](./Xiang_2013_Paper_Summary.md)
   - Focus: Corrosion in supercritical CO2 with impurities (SO2, O2, H2O)
   - Application: CCS pipeline design and safety

2. **Related CO2 Corrosion Research** (if available in other branches)
   - Additional papers on mechanistic modeling
   - Iron carbonate film formation studies
   - Experimental validation data

## Paper Summaries

### [Xiang_2013_Paper_Summary.md](./Xiang_2013_Paper_Summary.md)

Comprehensive analysis of the Xiang et al. (2013) paper including:

- **SIWDES Model:** Six-region mechanistic framework
  - Supercritical CO2
  - Interface
  - Water film
  - Deposition (product layer)
  - Electrodic (electrochemical)
  - Solid (steel substrate)

- **Key Findings:**
  - SO2 and O2 dramatically increase corrosion rates
  - Synergistic effects of multiple impurities
  - Critical role of water film chemistry
  - Predictive capability for CCS pipelines

- **Applications:**
  - Pipeline material selection
  - Operational guidelines for impurity control
  - Safety and integrity management
  - Economic optimization of CCS infrastructure

## Project Context

### Carbon Capture and Storage (CCS)

This research is essential for:
- **Climate Change Mitigation:** CCS reduces atmospheric CO2 emissions
- **Pipeline Safety:** Transporting supercritical CO2 requires corrosion-resistant infrastructure
- **Economic Viability:** Accurate corrosion prediction enables cost-effective design
- **Environmental Protection:** Preventing pipeline failures and CO2 leaks

### Impurities in CO2 Streams

CO2 captured from industrial processes often contains:
- **SO2** - from combustion of sulfur-containing fuels
- **O2** - residual oxygen from air separation processes
- **H2O** - moisture from flue gas or incomplete dehydration
- **NOx** - nitrogen oxides (less critical but present)

These impurities intensify corrosion and must be carefully controlled.

## Model Implementation

The mechanistic models described in these papers will be implemented in Python to:

1. **Predict corrosion rates** under various operating conditions
2. **Analyze concentration profiles** in water films and product layers
3. **Optimize design parameters** for CCS pipelines
4. **Assess safety margins** for different materials and environments

## Related Models

### Historical Development of CO2 Corrosion Models

- **de Waard & Milliams (1975):** First empirical model for CO2 corrosion
- **Nešić et al. (2003):** Mechanistic model with FeCO3 film formation
- **Xiang et al. (2013):** Extension to supercritical CO2 with impurities
- **Recent ML Approaches (2020s):** Machine learning for corrosion prediction

## References

### Primary Sources
- Xiang, Y., et al. (2013). Journal of Supercritical Fluids, 82, 1-12.
- Nesic, S. (2007). Corrosion Science, 49(12), 4308-4338.

### Additional Reading
- NACE Standards for CO2 corrosion
- IPCC reports on CCS technology
- Pipeline integrity management guidelines

## Usage Notes

For researchers and engineers working with this documentation:

1. **Start with:** [Xiang_2013_Paper_Summary.md](./Xiang_2013_Paper_Summary.md) for comprehensive overview
2. **Understand:** The SIWDES six-region framework before model implementation
3. **Apply:** Model equations to specific CCS pipeline scenarios
4. **Validate:** Compare predictions with experimental data when available

## Contributing

When adding new papers or documentation:
- Create detailed summaries in Markdown format
- Extract key equations and parameters
- Link to model implementation code
- Include validation data when available

---

*For questions or contributions, please refer to the main project README*
