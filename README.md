# Iron Corrosion Kinetics & Speciation Model 🧪⚙️

[![Python 3.7+](https://img.shields.io/badge/python-3.7+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A comprehensive Python-based numerical simulation model designed to evaluate the corrosion rate of Iron (Fe) in supercritical CO2 environment subjected to Sulfur Dioxide (SO₂) and Oxygen (O₂) atmospheres. 

This model simulates the complex interplay between  mass transfer, multi-species diffusion, electrochemical reaction kinetics, and the dynamic precipitation of porous corrosion product film.

##  Key Features

* **Equilibrium Speciation:** Calculates bulk liquid speciation and pH taking into account the dissociation of SO₂ into bisulfite (HSO₃⁻) and sulfite (SO₃²⁻) ions.
* **Multi-Species Transport:** Models the diffusion of critical species (O₂, SO₂, HSO₃⁻, SO₃²⁻, H⁺, SO₄²⁻, Fe²⁺) across the liquid and porous product films.
* **Electrochemical Kinetics:** Utilizes Tafel/Butler-Volmer electrochemical relaxation formulations to evaluate Fe dissolution and cathodic reductions processes.
* **Dynamic Film Growth:** Tracks the accumulation of solid precipitates (e.g., FeSO₃) and dynamically updates the moving boundary and film thickness.


##  Requirements & Dependencies

The model is built in Python and primarily relies on standard scientific computing libraries. To run the simulation, you will need:

* Python 3.7 or higher
* [NumPy](https://numpy.org/)
* [SciPy](https://scipy.org/)
* [Matplotlib](https://matplotlib.org/)

