# Cell-segmentation
A workflow for cell segmentation via Cellpose 3.0 and quantification of the mean intensity of a specific channel. The workflow includes image preprocessing, segmentation, results assessment and quantification. 
> Author: Yi Li
> 
> Supervisor: Gisele Miranda
> 
> Period: November - December 2024
> 
> SciLifeLab, KTH Royal Institute of Technology
> 

This repository is developed as part of the CB3050 _Project in Life Science_ course.

## Abstract

Environmental pollution caused by **micro- and nano-plastics (MNPs)** has put human health at huge risk. To explore the potential toxicological impact of MNPs on HepG2 cells and Huh-7 cells, image-based profiling was used to reveal the cell morphology and functional changes induced by MNP exposure, generating massive high-content images. However, a key challenge in processing such complex data is accurate cell segmentation, which is essential for profiling cellular features and performing other higher-level downstream analyses. Therefore, a deep learning-based tool, **Cellpose**, was chosen to segment HepG2 and Huh-7 cells. In this project, the quality of segmentation results is optimized by estimating the average cell diameters and adjusting the model parameter combination. The Cellpose model showed its convenience and efficiency in processing massive data. Based on the Cellpose-generated segmentation labels, the mean **Propidium Iodide (PI)** staining intensities for each cell were measured and its broad distribution indicates the damage to the cells induced by MNPs.
However, due to the lack of necessary manually annotated reference segmentations, the performance of Cellpose for cell segmentation in this project remains to be evaluated.

## Required Packages
- Cellpose 3.0  
Installation available at https://github.com/MouseLand/cellpose
- scikit-image 0.25.0
- scikit-learn 1.6.0
- numpy 2.0.2
- pandas 2.2.3
- matplotlib 3.9.3

## Repository content summary

| Filename |  Description|
|--|--|
|cellpose.ipynb  | Use the Cellpose 3.0 pre-trained model to process microscopy images with a nucleus channel and a cytoplasm channel, or grayscale images. The model predicts cell boundaries and generates labeled or binary masks, saving all results to a specified directory.|
|Jaccard index.ipynb  | Evaluate the segmentation results by comparing them to the loaded manual annotations or other files as "true" masks, and calculate the Jaccard index (JI) for every sample. The produced JIs and their corresponding sample numbers are saved as csv table to the specified directory. |
|mean_intensity.ipynb  | Measure the mean staining intensity in each cell based on the segmentation results. The generated mean intensities along with their corresponding sample numbers and label numbers are saved as csv tables to the specified directory.|

## Requirements for input data

We expect that the input images are in **tiff** format and their data type is **uint16**.
Compatible with both grayscale and RGB images. If your input consists of multiple grayscale images representing different channels, this pipeline can merge them into a single RGB image before segmenting. However, they must share the same prefix indicating the sample ID and have distinguishable suffixes to differentiate the channels. 
