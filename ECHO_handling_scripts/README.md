# Folder description

This folder contains scripts that handle:  
* The conversion of concentration files to the instructions for the ECHO machine.
* The extraction of information from the TECAN (mapping values back to the concentration array).

# Scripts description

## completed_concentration.ipynb

This notebook completes a concentration file without constant values (extract), by adding those columns values.

The notebook needs 3 inputs:  
* concentrations_line_A
* concentrations_example
* concentrations_line_P

The notebook generates 3 outputs:  
* concentrations_line_A_completed
* concentrations_example_completed
* concentrations_line_P_completed
 
**Notice:** Modified only the cocentration file, not the scripts for this.

## concentration_to_volume.ipynb

This notebook converts a concentration file to a volume file.

The notebook needs 3 inputs:  
* concentrations_line_A_completed
* concentrations_example_completed
* concentrations_line_P_completed

The notebook generates 3 outputs:  
* example_volumes
* line_A_volumes
* line_P_volumes

**Notice:**  
* Script is modified. Volumes are compatible.
* For easier pipetting later in the workflow, volume files can be sorted by water volume or amino acids volume so that high volumes are grouped together.

# volume_to_echo.ipynb

This notebook converts a volume file (example) to the following files

The notebook needs 2 inputs:  
* line_A_volumes
* line_P_volumes

The notebook generates 6 outputs:  
* example_named_volumes
* line_A_named_volumes
* line_P_named_volumes
* example_instructions
* example_water (for high volumes to pipette)
* example_aa (for high volumes to pipette)

**Notice:** Takes only volumes, no modification required.

# named_volumes_to_concentrations.ipynb

This notebook converts named volume files to named concentration files. 

The notebook needs 3 inputs:  
* example_named_volumes
* line_A_named_volumes
* line_P_named_volumes

The notebook generates 3 outputs:  
* example_concentrations_reconstituted
* line_A_concentrations_reconstituted
* line_P_concentrations_reconstituted

**Notice:** Works. Concentrations need to be merged (by order of well name, line_A at the top of the file and line_P at the bottom).

# extract_yield.ipynb

The notebook needs 2 inputs:  
* Raw results from a TECAN (example_TECAN)
* Reconstituted concentrations from the previous step.

The notebook generates 5 outputs:  
* yield_and_std
* outliers (returns outliers)
* everything: all results in the same file
* std, ratio, mean: draw the plaque with std, ratio between mean and std and mean to see whether outliers are localised on the plaque
* comments: about outliers