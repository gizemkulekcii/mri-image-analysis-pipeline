Preprocessing(preprocessing.m): Preprocessing done using MATLAB and SPM12. Preprocessing on T1-weighted images and ToF images to obtain skull stripped ToF images. Performs tissue segmentation, brain masking, coregistration, and applying binary masks to anatomical.

Vessel Segmentation (segmentation.py):

You can find an information about the small vessel segmentation pipeline (Omelette) here :
- https://cds.ismrm.org/protected/21MProceedings/PDFfiles/3745.html 

The image2segmentation function is taken from the following link:
- https://gitlab.com/hmattern/omelette/-/blob/master/data_and_results/benchmark/Script_Segmentation.py?ref_type=heads

Vessel Distance Mapping (VDM): Combining vessel segmentation results with binary hippocampus masks to calculate distance from each hippocampal voxel to nearest blood vessel

Statistics(statistics_b04.R): Correlation and regression models

This project aims to investigate the relationship between hippocampal vessel distance, cognitive performance, and hippocampal volume in cognitively normal older adults. Specifically, it aims to:
1. Quantify hippocampal vessel distance using VDM
2. Analyze the association between vessel distance and cognitive performance
3. Examine the relationship between vessel distance and hippocampal volume.
4. Investigate the relationship between vessel distance and demographic factors (age, sex, education), as well as physical fitness (VO2 max).

Methods
1. Preprocessing:
Image preprocessing were performed on an T1-weighted images and ToF images to obtain skull stripped ToF images for vessel segmentation using the Omelette pipeline. Preprocessing was done using MA TLAB and SPM12. First tissue segmentation was performed on an anatomical MRI image, generating tissue probability maps. From these maps, a brain mask was created, including only voxels with a combined probability above 0.9. Post-processing was applied to enhance mask quality by filling holes, removing noise, and smoothing edges. Then, coregistration was performed to align ToF and T1-weighted images into a common reference space. The brain mask was applied to both T1 and TOF images, creating skull-stripped versions.

2. Vessel segmentation: The preprocessed, skull-stripped ToF images were processed with
the small vessel segmentation pipeline "Omelette," written by Hendrik Mattern.

3. Hippocampal Volumetry: Hippocampal volumes were pre-extracted using the Automated Segmentation of Hippocampal Subfields (ASHS) technique. Quality control was performed on these segmentations. Binary hippocampus masks were created from the automatic segmentations. Coregistration of T2-weighted and ToF images to the T1-weighted space was performed to ensure accuracy. Large segmentation errors were corrected, while minor errors were not addressed due to time constraints.

4. Vessel Distance Mapping (VDM): VDM was performed by combining vessel segmentation results with binary hippocampus masks to calculate the distance from each hippocampal voxel to the nearest blood vessel.
5. 
6. Statistical Analysis: Statistical analyses, including correlation and regression models, were conducted to examine the relationships between hippocampal vessel distance, cognitive performance, hippocampal volume, and physical fitness. Demographic factors (age, sex, education) were included as covariates in all analyses, except hippocampal volume.
