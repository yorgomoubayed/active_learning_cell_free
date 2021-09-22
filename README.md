Author: Mathilde Koch, Faulon's group, INRAe.

# Description

This repository aims to regroup all necessary scripts for generating data and models presented in:

Large scale active-learning-guided exploration to maximize cell-free production by Olivier Borkowski*, Mathilde Koch*, Agnès Zettor, Amir Pandi, Angelo Cardoso Batista, Paul Soudier and Jean-Loup Faulon. Currently available at https://doi.org/10.1101/751669. *: authors contributed equally.

# Active learning loop

This folder contains data both for: 
- Generating the active learning loop **(learn_and_suggest script, Figures 1c and 1d)**.
- Generating the model statistics at each iteration **(generate_model_statistics, Figure 1e)**.
- Generating the first plate to perform active learning **(initial_plate_generation, Figure 1c)**.

# Compound effect analysis

Contains scripts to analyze the effect of compounds in different lysates with a linear regression or mutual information. **(Figure 1g, Supplementary Figure 3)**.

# Controls analysis plates

This folder contains the data and scripts used to extract absolute yields (ie: compared to lysate of origin) for all other lysates. **(Supplementary Figure 4)**.

# Echo handling scripts

This folder contains scripts for handling the Echo liquid handler. From a file of concentrations to test, to the instructions to the machine, to data extraction and quality control. **(No specific Figure)**

# Multiple extracts analysis

This folder contains scripts to extract the most informative 20 points to predict 102 other points, as well as various analyses than were conducted using those 20 points. **(Figure 2 and Supplementary Figure 2e)**.

# Predict for new lysate

This folder contains scripts to predict yield on unseen lysates to optimise them. **(No specific Figure, but same data as Figure 2)**.

# Whole lysate most informative points

The aim of this folder is to extract the most informative 102 (or 20) points that enabled the prediction of the full 1017 points dataset **(Supplementary Figure 2)**. Functions are similar to the ones that do the same thing in "multiple_extract" analysis. The difference is the wrapping around the input concentrations to test, or data to compare to.

# Requirements

## Packages required

- **nb_conda_kernels :** running the Jupyter notebook in the correct environment.
- **jupyter_contrib_nbextensions :** tools for better Jupyter notebooks.
~~~
conda install -c conda-forge jupyter_contrib_nbextensions
~~~
- **Numpy :** array handling.
- **Matplotlib :** data visualisation.
- **Scikit-learn :** machine learning algorithms. **Version 0.19.1** is recommended.

## Conda environment

~~~
conda env create -f alcf.yml
~~~

~~~
conda activate alcf
~~~