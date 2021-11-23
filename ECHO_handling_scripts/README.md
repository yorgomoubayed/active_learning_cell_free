# Folder

This folder contains scripts that handle:  
* The conversion of concentration files to the instructions for the ECHO liquid handler.
* The extraction of information from the TECAN (mapping values back to the concentration array).

# Scripts

## completed_concentration.ipynb

This notebook completes a concentration file that doesn't have constant values (extract), by adding those values.

The notebook needs 1 inputs:  
* concentrations_{}.csv

The notebook generates 1 output:  
* concentrations_{}_completed.csv
 
**Notice:** Modified only the cocentration file, not the scripts for this.

## concentration_to_volume.ipynb

This notebook converts a concentration file to a volume file.

The notebook needs 3 inputs:  
* concentrations_line_A_completed.csv
* concentrations_example_completed.csv
* concentrations_line_P_completed.csv

The notebook generates 3 outputs:  
* example_volumes.csv
* line_A_volumes.csv
* line_P_volumes.csv

**Notice:**  
* Script is modified. Volumes are compatible.
* For easier pipetting later in the workflow, volume files can be sorted by water volume or amino acids volume so that high volumes are grouped together.

# volume_to_echo.ipynb

This notebook converts a volume file (example).

The notebook needs 2 inputs:
* line_A_volumes.csv
* line_P_volumes.csv
* example_volumes.csv

The notebook generates 6 outputs:  
* line_A_named_volumes.csv
* line_P_named_volumes.csv
* example_named_volumes.csv
* example_instructions.csv
* example_water.csv (for high volumes to pipette)
* example_aa.csv (for high volumes to pipette)

**Notice:** Takes only volumes, no modification required.

# named_volumes_to_concentrations.ipynb

This notebook converts named volume files to named concentration files. 

The notebook needs 3 inputs:  
* example_named_volumes.csv
* line_A_named_volumes.csv
* line_P_named_volumes.csv

The notebook generates 3 outputs:  
* example_concentrations_reconstituted.csv
* line_A_concentrations_reconstituted.csv
* line_P_concentrations_reconstituted.csv

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
