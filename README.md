# Cell-segmentation
A workflow for cell segmentation via Cellpose 3.0 and quantification of the mean intensity of a specific channel. The workflow includes image preprocessing, segmentation, results assessment and quantification. 
> Author: Yi Li
> Supervisor: Gisele Miranda
> Period: November - December 2024
> SciLifeLab, KTH Royal Institute of Technology

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
