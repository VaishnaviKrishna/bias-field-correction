# Bias field correction
## Introduction and Motivation
* The intensity inhomogeniety in medical imaging that arises from magnetic settings, patients’ position etc is known as a bias field
* The intensity of the same tissue should always be similar in one image and not vary with the location of the tissue
* This property can facilitate the procedures in many automated techniques such as segmentation, classification and registration and make the results reasonable

## Procedure
MRI images obtained by the application of very strong magnetic fields are generally corrupted by bias field, a very low frequency and smooth signal that gradually changes over the image.  In this project, a bias field correction technique is developed using neural networks. The skull stripped 3D volumes of the cortical surface of the brain obtained post surface and volume registration method of BrainSuite software are sliced along the sagittal,coronal and axial plane to obtain 2D gray scale images of the brain. These images are then fed to an encoder-decoder unit comprising of 3 hidden layers each. For our purpose, instead of reconstructing the original T-1 weighted MRI images, the auto-encoder is trained to output an approximation of the bias field which in turn is used to restore the corrupted MRI images. Further, the latter can be used to classify and segment the brain tissues and detect abnormalities in the brain.
The **flowchart.png** in the images folder show the diagrammatic representation of the procedure explained above.

# Overview
The bias field estimation and reconstrucion of corrected MRI images are done in two separate notebooks:
* autoencoder_bias_field_estimation.ipynb
* autoencoder_3axes_merged_reconstructed_mri.ipynb
# Examples
* The images below show the inputs to autoencoder (in the first row) and the bias field ground truths (in the second row) against which it was trained

<img src="images/mri%20images/1.jpg" width=250> <img src="images/mri%20images/2.jpg" width=250>
<img src="images/mri%20images/3.jpg" width=250> <img src="images/bias%20field/1.jpg" width=250> 
<img src="images/bias%20field/2.jpg" width=250> <img src="images/bias%20field/3.jpg" width=250> 
