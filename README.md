# tumor-analysis

I developed this project as part of my project-1 for my university.

This project introduces an automated brain tumor segmentation system from deep learning that utilizes a 3D U-Net convolutional neural network. Essentially, the mechanism can perform very accurate voxel-level classification as well as volumetric quantification of tumor subregions directly from multimodal 3D MRI scans. Thus, the system becomes a very efficient and reproducible way to analyze clinical and research data.

In detail, the model was trained as well as tested on the Brain Tumor Segmentation 2023 (BraTS23) dataset which is the result of the collaboration between the Center for Biomedical Image Computing and Analytics and the
University of Pennsylvania. This fully annotated dataset consists of glioma MRI volumes acquired from multiple institutions and each subject has four
modalities—T1, T1ce, T2, and FLAIR. Besides that, the preprocessing stage involves skull-stripping, registration to a common anatomical space, resampling to 1 mm³ isotropic voxel spacing, and intensity normalization for cross-image coherence.

Conceptually, the proposed architecture is a modular five-stage pipeline going through the steps of data ingestion, preprocessing, 3D U-Net segmentation, analysis, and output generation. Moreover, this structure allows for flexible experimentation, independent/module-wise optimization, and still end-to-end integration. The Dice similarity coefficient (DSC) was the main performance measurement of the model as it is the most sensitive to background class imbalance, which is a medical image segmentation problem.

The experimental results reveal that the system manages to delineate accurately all tumor subregions, thus the overall tumor Dice has been averaged to 0.9231, the macro F1 score to 0.9123, and the voxel-level accuracy to 0.9907. The model's delineations of tumor boundaries across different patient anatomies were confirmed both visually and quantitatively. Slightly insufficient segmentation was detected in the enhancing tumor (ET) area, thus the Dice score of ~0.865 was achieved, which is in line with difficulty faced in related literature of BraTS where ET is frequently reported below 0.85.

Summing up, the present research serves as the basis of a 3D U-Net volumetric tumor segmentation pipeline able to perform near state-of-the-art and be generalized on real MRI data from practical scenarios. The pipeline represents a reproducible as well as a computationally efficient framework that can be of use in clinical practice, and also, can motivate further research in neuro-oncological imaging.
