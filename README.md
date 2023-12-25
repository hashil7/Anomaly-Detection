# Anomaly-Detection
Anomaly detection in images using deep learning model : Auto encoder
The dataset consists of images of uninfected and malarial infected cells
ALGORITHM DESCRIPTION
The data to the auto encoder is fed as a batch of images, using data generators, where the
train generator is a batch of uninfected images, the validation generator consists of uninfected 
images and the test generator produces a batch consisting of both parasitized and uninfected 
image.
KDE and reconstruction error are the statistical quantities used for making the decision 
boundary for the model to differentiate anomalies from non anomalies.
The reconstruction error of images with anomaly is high. But we cannot use reconstruction 
error alone as an effective parameter, as it also depends on the image, i.e., the image may be 
contaminated with outliers. In order to counteract this effect, an adversarial autoencoder
architecture is adapted, which imposes a prior distribution on the latent representation, 
typically placing anomalies into low likelihood-regions. Utilizing the likelihood model, 
potential anomalies can be identified and rejected already during training, which results in an 
anomaly detector that is significantly more robust to the presence of outliers during training.
The parameter, Kernel Density estimation (KDE), is used to calculate the likelihood of an 
image belonging to the good class. KDE provides an estimate of where the input image 
vector space lies in the latent space. It is assumed that the anomaly images have densities
farther away from the densities of training images. To identify the anomalies, a threshold is 
set on KDE and reconstruction error. The threshold values will be chosen based on the
performance using few observations using good and anomaly data.
The basic idea is to create an adversarial auto encoder which consists of an encoder and a 
decoder for anomaly detection in images. The encoder reduces the feature size, whereas, the 
decoder increases the feature size. The KDE is estimated at the bottleneck layer, i.e., after the 
data is completely passed through the encoder. Bottle neck layer in the context of Deep 
Learning, is a layer within a neural network architecture that is designed to have a
significantly lower number of filters or neurons compared to the layers that precede and
follow it. The model decides the image to be an anomaly if either the KDE is lesser than the 
density threshold or the reconstruction error is greater than the reconstruction error threshold. 
