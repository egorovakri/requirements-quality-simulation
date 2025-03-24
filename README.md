# Requirements Quality Simulation

This Python script simulates the impact of requirements quality attributes on project delays. It models a project's progress through multiple cycles (sprints), considering factors like complexity, completeness, correctness, verifiability, and feasibility of requirements. The simulation calculates the total project delay based on these factors and visualizes the results.

---

## Table of Contents

- [Description](#description)
- [Installation](#installation)
- [Usage](#usage)
- [Simulation Parameters](#simulation-parameters)
- [Quality Attributes](#quality-attributes)
- [Complexity Levels](#complexity-levels)
- [Results](#results)
- [Visualization](#visualization)
- [Dependencies](#dependencies)

---

## Description

The script simulates a project's development lifecycle, where requirements are implemented in sprints. It assesses how different quality attributes—completeness, correctness, verifiability, and feasibility—influence overall project delay. It generates a CSV file with the results and creates 3D surface plots to visualize the relationships.

---

## Installation

Ensure you have Python 3.6 or later installed. Then, install the required libraries:

```bash
pip install numpy pandas matplotlib scipy
```
## Usage

1. Clone the repository to your local machine.

2. Open the Jupyter Notebook (`Requirements-Simulation.ipynb`) in your preferred environment (e.g., Jupyter Notebook, JupyterLab, or VS Code).

3. Run the single cell in the notebook. This cell will:
   - Execute the simulation for various requirements quality attributes and project complexities.
   - Generate and display six 3D surface plots.
   - Save the simulation results to a CSV file named `simulation_results.csv`.

4. Review the cell to see the simulation parameters, code, and outputs.

## Simulation Parameters

The simulation uses the following parameters:

* `initial_defect_rate`: 0.15
* `max_cycles`: 50 (maximum number of simulation cycles or sprints)
* `min_defect_rate`: 0.01
* `requirements_per_sprint`: 40
* `bug_fixing_probability`: 0.3 (probability that a sprint focuses on fixing bugs)

## Quality Attributes

The simulation considers the following quality attributes:

* `Unambiguous`: Fixed values for quality factor, risk, and probability.
* `Complete`: Variable completeness value (Low: 0.3, Medium: 0.6, High: 0.9).
* `Correct`: Variable correctness value (Low: 0.3, Medium: 0.6, High: 0.9).
* `Consistent`: Fixed values for quality factor, risk, and probability.
* `Feasible`: Binary feasibility value (0 or 1).
* `Verifiable`: Variable verifiability value (Low: 0.3, Medium: 0.6, High: 0.9).

## Complexity Levels

The simulation models three levels of project complexity:

* `Low`: 50 requirements.
* `Medium`: 200 requirements.
* `High`: 500 requirements.

## Results

The simulation results are stored in a Pandas DataFrame and saved to `simulation_results.csv`. The DataFrame includes the following columns:

* `Complexity`: Complexity level.
* `Completeness`: Completeness value.
* `Correctness`: Correctness value.
* `Verifiability`: Verifiability value.
* `Feasibility`: Feasibility value.
* `Total Delay (Days)`: Total project delay in days.

Sample output:

```python
    Complexity  Completeness  Correctness  Verifiability  Feasibility  Total Delay (Days)
0          Low           0.3          0.3            0.3            0                35.0
1          Low           0.3          0.3            0.3            1                30.0
2          Low           0.3          0.3            0.6            0                33.5
3          Low           0.3          0.3            0.6            1                28.5
4          Low           0.3          0.3            0.9            0                32.0...
Total: 106 rows x 6 columns
```
## Visualization

The script generates six 3D surface plots to visualize the impact of quality attributes on project delays:

* Completeness vs. Correctness vs. Total Delay (Days) for Low, Medium, and High complexity projects.
* Verifiability vs. Feasibility vs. Total Delay (Days) for Low, Medium, and High complexity projects.

All plots use the `coolwarm` colormap, and the Z-axis (Total Delay) is scaled consistently across all graphs to facilitate comparison.

## Dependencies

* `numpy`: For numerical computations.
* `pandas`: For data manipulation and storage.
* `matplotlib`: For plotting.
* `scipy`: For grid data interpolation.
