# Description
This folder contains all data files and scripts to generate Figures 1c, 1d and 1e of the paper.

## Folders
* **data/:** contains whole data (plates and compounds) from this study.
* **data/no_controls:** data from rows B to O, **without controls from rows A and P**.
* **model_statistics/model_statistics_small:** data (csv/png) generated from the **generate_model_statistics.ipynb** notebook.
* **echo_files/:** initial plates generated from the **initial_plate_generation.ipynb** notebook.

## Files
* **initial_plate_generation.ipynb:** Jupyter notebook that generates the initial training set (or initial plate).
* **learn_and_suggest.ipynb:** Jupyter notebook that generates the active leaning loop.
* **generate_model_statistics.ipynb:** Jupyter notebook that generates model statistics (5 fold cross validation).

## Running scripts

* Clone repository

* Create conda environment form the YAML file (it has all packages and dependencies)
~~~
conda env create -f alcf.yml
~~~

* Activate conda environment
~~~
conda activate alcf
~~~

* Launch Jupyter Notebook
~~~
jupyter notebook <notebook nama>
~~~