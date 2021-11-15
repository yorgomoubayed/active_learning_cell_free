# Description

This folder contains scripts to analyse control data to obtain normalised results  with the same yield (global yield in the accompanying paper, Supplementary Figure 4). Each extract should be subtracted its own zero, whereas reference should be substracted the its zero. The formula to use therefore becomes: 

**yield = (GFP - autofluo_local)/(ref_ORI - autofluo_ORI)**		

We can then use the normalised yields from the control plates to normalise other plates.

# Folders and files

All 8 folders contain the following Jupyter notebooks:
* **Extract_yield_own_autofluo.ipynb:** extracts the yield values compared to the current plate, with the correct autofluorescence subtracted.
* **extracting_duplicates.ipynb:** takes an input file with data from 2+ plates and compares duplicates. **See any ''compare_name'' for example**.
* **analysing_duplicates.ipynb:** calculates R2 of the 'raw yield': normalised each from its own plate, and regressions.

**Notice:** 
* Each concerned folder contains normalised data.
* Reference to ORI is in data_plate_ORI.
* Reference to PS is in data_plate_PS. 
* Data is copy pasted from those plates to the comparison plate in other datasets. These are used to normalise.

# Analysis

## AB analysis

The normalisation we proceed to is:  
y_norm_to_ORI = a * y_norm_to_AB + b  
normalised_to_ORI = 0.72 * normalised_to_AB + 0.0  

## DH5alpha analysis

The normalisation we proceed to is:  
y_norm_to_ORI = a * y_norm_to_DH5 + b  
normalised_to_ORI = 1.54 * normalised_to_DH5 + 0.38  

## PS analysis

The normalisation we proceed to is:  
y_norm_to_ORI = a * y_norm_to_PS + b  		

2 different plates can be compared from 'raw' data: the **full PS plate** and the **control PS plate** are both normalised according to PS. It is interesting to note that the controls are very well conserved with a R2 of 0.9378.

The coefficients are slightly different for the **full plate** and the **control plate**:		
* **Full plate:** normalised_to_ORI = 1.29 * normalised_to_PS_full + 0.08  	
* **Control plate:** normalised_to_ORI = 1.19 * normalised_to_PS_ctrl + 0.00  		

## Rifaxamin analysis 

The normalisation we proceed to is:  
rifaxamin_to_PS = 0.07 * rifaxamin_to_rifaxamin + 0.02  
rifaxamin_to_ORI = 1.19 * rifaxamin_to_PS + 0.00  

## Spectinomycin analysis

The normalisation we proceed to is:  
spectinomycin_to_PS = 0.15 * spectinomycin_to_spectinomycin + 0.03  
spectinomycin_to_ORI = 1.19 * spectinomycin_to_PS + 0.00  
		
**Notice:** regression R2 is the lowest of the current workflow at 0.87.