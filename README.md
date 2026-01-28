
# Files for Submission

This directory contains the implementation and data files for the RDE-DA-SHRED project, which focuses on rotating detonation engine (RDE) simulation and data-driven modeling.

## Contents

### Main Implementation Files

- **`Cheap2Rich.py`** - Core implementation of the data-driven model that transforms low-fidelity simulations to high-fidelity predictions
- **`baselines_for_results.ipynb`** - Jupyter notebook containing baseline comparisons and results visualization

### Data Files

- **`high_fidelity_1d_dataset.npy`** - High-fidelity simulation dataset (1D)
- **`Kochs_model_dataset.npy`** - Raw dataset from Koch's model

- **`high_fidelity_sim_processed.npy`** - Processed high-fidelity simulation data
- **`Koch_model_processed.npy`** - Processed data from Koch's model

### Configuration

- **`requirements.txt`** - Python package dependencies required to run the code

### Koch Model Data Generation

The `Koch_model_data_generation/` subdirectory contains utilities for generating data with Koch's model :

- **`euler_1D_py.py`** - 1D Euler equation solver implementation
- **`rde1d_3_waves.py`** - RDE simulation with 3-wave configuration
- **`how_to_generate_data.md`** - Instructions for generating new simulation data

the output of `rde1d_3_waves.py` should be a 'Kochs_model_dataset.npy' file which weights over 160MB (hence it is not attached to the submission). It is preprocessed in the first cells of the `baselines_for_results.ipynb` notebook, so running the notebook first is recommended. Alternatively, the preprocessed datasets from both high fidelity and low fidelity simulations are attached and can be found in **`high_fidelity_sim_processed.npy`**, **`Koch_model_processed.npy`** and used for baselines and the Cheap2Rich model.

## Getting Started

1. Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```

2. Review the baseline results notebook to understand the approach

3. Run the main model using `Cheap2Rich.py`

4. (Optional) Generate new training data using scripts in `Koch_model_data_generation/`
