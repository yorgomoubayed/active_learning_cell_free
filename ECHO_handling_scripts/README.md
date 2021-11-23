# Folder

This folder contains scripts that handle:  
* The conversion of concentration files to the instructions for the ECHO liquid handler.
* The extraction of information from the TECAN (mapping values back to the concentration array).

# Scripts

## completed_concentration.ipynb

Completes a concentration file that doesn't have constant values (extract), by adding those values.

* **Input:** concentrations_{}.csv
* **Output:** concentrations_{}_completed.csv
 	
**Notice:** Modified only the cocentration file, not the scripts for this.

## concentration_to_volume.ipynb

Converts a concentration file to a volume file.

* **Input:** concentrations_{}_completed.csv
* **Output:** {}_volumes.csv

**Notice:**  
* Script is modified. Volumes are compatible.
* For easier pipetting later in the workflow, volume files can be sorted by water volume or amino acids volume so that high volumes are grouped together.

# volume_to_echo.ipynb

Converts a volume file (example).

* **Input:** {}_volumes.csv
* **Output:**    
	* {}_named_volumes.csv
	* {}_instructions.csv
	* {}_water.csv (for high volumes to pipette)
	* {}_aa.csv (for high volumes to pipette)

**Notice:** Takes only volumes, no modification required.

# named_volumes_to_concentrations.ipynb

This notebook converts named volume files to named concentration files. 

**Input:** {}_named_volumes.csv
**Output:** {}_concentrations_reconstituted.csv

**Notice:** Concentrations need to be merged (by order of well name, line_A at the top of the file and line_P at the bottom).

# extract_yield.ipynb

The notebook needs 4 inputs:  
* example_TECAN.csv: raw results from a TECAN plate reader.
* example_concentrations_reconstituted.csv
* line_A_concentrations_reconstituted.csv
* line_P_concentrations_reconstituted.csv

The notebook generates 7 outputs:  
* example_yield_and_std.csv
* example_outliers.csv
* example_draw_mean.csv
* example_draw_ratio.csv
* example_draw_std.csv
* example_everything.csv: all results collected in the same file.
* example_comments.txt: comments about outliers.
