**Fork Changes**
1. Compatibility with tf2
2. If rotation is applied, always perform up to 180° rotations regardless of magnitude and randomly mirror the image

**Original readme**

*Updated. Repository under construction.*

This repository includes the implementation of a method proposed in **"Tailoring automated data augmentation to H&E-stained histopathology"** accepted to MIDL 2021.

**Abstract**

Convolutional neural networks (CNN) are sensitive to domain shifts, which can result in poor generalization.  In medical imaging, data acquisition conditions differ among institutions, which leads to variations in image properties and thus domain shift.  Stain variation in histopathological slides is a prominent example.  Data augmentation is one way to make CNNs robust to varying forms of domain shift but requires extensive hyperparameter tuning.   Due  to  the  large  search  space,  this  is  cumbersome  and  often  leads  to  suboptimal generalization  performance.   In  this  work,  we  focus  on  automated  and  computationally efficient data augmentation policy selection for histopathological slides.  Building upon the RandAugment framework, we introduce several domain-specific modifications relevant to histopathological images, increasing generalizability.  We test these modifications on H&E-stained histopathology slides from Camelyon17 dataset. Our proposed framework outper-forms the state-of-the-art manually engineered data augmentation strategy, achieving an area under the ROC curve of 0.964 compared to 0.958, respectively.

<div align="center">
    <img src="/he-randaugment/augmentations_new.png" width="900px"</img> 
</div>

**Methodology**

**Code instructions**

To run the code:
```
launch_experiment.py dataset_dir output_dir experiment_tag trial_tag n_epochs batch_size lr randaugment rand_m rand_n ra_type v1_type v2_type t1_type t2_type
```
To use the modified version of randaugment standalone you can apply the distort_image_with_randaugment.py function to each image in the training batch, providing following arguments magnitude (m), number of sequentially applied transforms (n or num_layers), type of a transform set (ra_type= 'Default') for transforms used in this paper. 
```
distort_image_with_randaugment(image, m, n, ra_type)
``` 

**Notes**

In case of any questions, please contact: khrystyna.faryna@gmail.com
