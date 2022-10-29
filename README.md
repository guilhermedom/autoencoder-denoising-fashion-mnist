# Autoencoder Denoising Fashion MNIST

Convolutional autoencoder removing noise from Fashion MNIST clothing images.

---

## Problem Overview

[Fashion MNIST] is a dataset having 70,000 images of 10 different types of clothing. Each type of clothing constitutes a class. The dataset was proposed to substitute the original MNIST dataset, which has handwritten digits images for the 10 numeric digits. MNIST is generally considered too easy and not representative of the 2020s challenges in computer vision. Hence, Fashion MNIST brings a tougher trial to computer vision models and also is a dataset more closely related to real-world problems. Thinking about Fashion MNIST as a relevant dataset for modern computer vision analyses, we can use it for other tasks not related to classification, like image denoising. Below there is a selection of images from Fashion MNIST:

![autoenconder_denoising_fashion_mnist_grid](https://user-images.githubusercontent.com/33037020/198778465-615697dd-c05f-4838-9f8b-9819fcbfe289.PNG)

Noise and outliers are unwanted artifacts in data that can heavily disturb the performance of a model or mess up analyses being done on the dataset. For this reason, many algorithms have been proposed to remove noise and outliers from data, including [K-Means], [kNN], [DBSCAN] and others.

Specifically talking about noise removal in images, many algorithms have been proposed, such as [wavelet transform], [anisotropic diffusion], [non-local means] and others. These algorithms, although being good on the task, have limited generalizing capabilities, may need parameter fine tuning and are not easily transferable to be applied on images with core differences.

## Analysis Introduction

[Autoencoders] are types of neural networks that can compress and decompress data by reducing its dimensionality or overall size. Autoencoders have this ability because they are able to capture the most relevant features in the data and represent them in a more simple manner. This is also true for image data, especially considering that current machine learning libraries make it easy to add convolutional layers to autoencoders.

[Convolutional layers] are closely related with the revolution in computer vision caused by deep learning. Deep learning consists of models with many layers of neurons extracting features and interpreting them. Convolutions are the most common type of layer used for feature extraction; they have proved their proficiency in extracting information from images.

Autoencoders combined with convolutional layers can extract the most useful features in images, even if they have noise. Therefore, it is possible to use this combination to remove noise from images by filtering all the worthless information in the first phase. In the second phase, the original image is reconstructed using only relevant features learned before. In this way, convolutional autoencoders can provide image noise reduction to boost the performance of any computer vision model.

Here we develop a convolutional autoencoder able to remove all noise from a noisy version of Fashion MNIST. Although the denoised images do not look perfect, they still preserve the main aspects of their original noise-free versions and are still understandable:

![autoenconder_denoising_fashion_mnist_denoised_grid](https://user-images.githubusercontent.com/33037020/198778549-8a154d2a-cd8d-4cae-b992-cc13e013df0d.PNG)

[//]: #

[Fashion MNIST]: <https://www.kaggle.com/datasets/zalando-research/fashionmnist>
[k-means]: <https://ieeexplore.ieee.org/document/7164681>
[knn]: <https://www.researchgate.net/publication/220931795_Image_Denoising_with_k-nearest_Neighbor_and_Support_Vector_Regression>
[dbscan]: <https://www.researchgate.net/publication/327169935_A_system_based_on_Hadoop_for_radar_data_analysis>
[wavelet transform]: <https://www.mathworks.com/help/wavelet/ug/wavelet-denoising.html>
[non-local means]: <http://www.ipol.im/pub/art/2011/bcm_nlm/>
[anisotropic diffusion]: <https://www.sciencedirect.com/science/article/abs/pii/S1047320312000259>
[autoencoders]: <https://en.wikipedia.org/wiki/Autoencoder>
[convolutional layers]: <https://www.ibm.com/cloud/learn/convolutional-neural-networks>
