# Optimal Energy Consuming on Spraying an Agricultural Field by Using Multiple UAVs

This repository contains the code and research paper for the study *Optimal Energy Consuming on Spraying an Agricultural Field by Using Multiple UAVs.* This project focuses on optimizing UAV energy consumption to efficiently spray agricultural fields by minimizing flight time through clustering and route optimization.

## Table of Contents

- [Introduction](#introduction)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Methodology](#methodology)
- [Results](#results)
- [Citation](#citation)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## Introduction

With the increasing need for sustainable agriculture, energy-efficient methods for field spraying are essential. This study proposes an approach for optimizing UAV energy use by minimizing flight distances across spraying zones through clustering and route optimization techniques. The study compares classical segmentation with AI-driven clustering methods to determine the most effective approach for reducing UAV flight times.

This research is published in *Agriculture Digitalization and Organic Production* by Springer, and it explores UAV-based precision spraying in agricultural applications.

## Project Structure

The repository includes the following files:

Optimal_Energy_UAV_Spraying/ ├── docs/ │ └── Optimal Energy Consuming on Spraying Multiple UAVs.pdf # Research paper ├── src/ │ └── Optimal Energy Consuming UAV.jl # Julia code for optimization ├── README.md # Project documentation └── LICENSE # License information


- **docs/**: Contains the research paper.
- **src/**: Contains the Julia script for running the optimization model.
- **README.md**: Provides an overview, installation instructions, and usage details.
- **LICENSE**: Specifies the license information for this project.

## Installation

To set up and run the code, install [Julia](https://julialang.org/) and required packages. Follow these steps:

1. **Install Julia**:
   - Download and install Julia from [https://julialang.org/downloads/](https://julialang.org/downloads/).

2. **Install Required Julia Packages**:
   - Open the Julia REPL and install the necessary packages:
     ```julia
     using Pkg
     Pkg.add("JuMP")
     Pkg.add("Clustering")
     Pkg.add("Distances")
     Pkg.add("Gurobi") # Note: Gurobi requires a license (see below).
     ```
   - **Gurobi License**:
     - Obtain and set up a Gurobi license from [https://www.gurobi.com/](https://www.gurobi.com/).

## Usage

1. **Clone the Repository**:
   - In a terminal, clone the repository and navigate to the `src` directory:
     ```bash
     git clone https://github.com/yourusername/Optimal_Energy_UAV_Spraying.git
     cd Optimal_Energy_UAV_Spraying/src
     ```

2. **Run the Julia Code**:
   - Open Julia in the `src` directory and execute the code:
     ```julia
     include("Optimal Energy Consuming UAV.jl")
     ```
   - The code will calculate optimized UAV routes, minimizing energy consumption based on specified parameters.

## Methodology

The approach involves dividing the field into zones and then calculating optimal flight paths for UAVs. Two main methods are applied:

1. **Classical Segmentation**: The field is divided into four sections, with each UAV spraying within its assigned region.
2. **K-Means Clustering**: UAVs spray based on clusters optimized by the K-Means algorithm.

Within each cluster, UAV routes are optimized using the **2-Opt Heuristic** for the Traveling Salesman Problem (TSP), minimizing travel distances and overall energy consumption.

### Parameters
- **Field Dimensions**: Length and width of the spraying area.
- **UAV Speed and Spray Rate**: Parameters for each UAV to optimize energy efficiency.

## Results

The model demonstrates that clustering with the K-Means method improves flight efficiency by an average of 19% over classical segmentation. This approach effectively reduces unnecessary flight time, enhancing energy efficiency and extending UAV operational life.

## Citation

If you use this research or code in your work, please cite it as follows:

Güzey, A., Akıncı, M.M., & Güzey, H.M. (2022). Optimal Energy Consuming on Spraying an Agricultural Field by Using Multiple UAVs. In Agriculture Digitalization and Organic Production. Springer. DOI: 10.1007/978-981-16-3349-2_24


## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

This research was funded by TUBITAK (Project No. 217E138) as part of the ERANET project *HARMONIC*. Special thanks to all contributors who supported this study.

