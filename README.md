Preprocessing((preprocessing.m): Preprocessing done using MATLAB and SPM12. Preprocessing on T1-weighted images and ToF images to obtain skull stripped ToF images.

Vessel Segmentation (segmentation.py):

You can find an information about the small vessel segmentation pipeline (Omelette) here :
- https://cds.ismrm.org/protected/21MProceedings/PDFfiles/3745.html 

The image2segmentation function is taken from the following link:
- https://gitlab.com/hmattern/omelette/-/blob/master/data_and_results/benchmark/Script_Segmentation.py?ref_type=heads

Vessel Distance Mapping (VDM): Combining vessel segmentation results with binary hippocampus masks to calculate distance from each hippocampal voxel to nearest blood vessel

Statistics: Correlation and regression models


