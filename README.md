# Using computer vision to detect if bike lanes are blocked

Hi! If you understand deep learning and would like to collaborate, feel free to skip to the "Challenges" section.

### Problem
Per the [website](http://parkingdirty.com "Parking Dirty"), Parking Dirty is a project to crowd-source data on Arlington, VA's frequently-blocked bike lanes.

The website displays screenshots of traffic cameras to users. Users then records whether the bike lane is blocked.

The data is a zip file with two folders in it - "blocked" and "notblocked". All of the photos in the blocked folder have been classified by humans as having a blocked bike lane.

The single camera dataset contains about 3,600 images and is about 500MB in size. The "all cameras" set contains all the classified images across several intersections. It contains about 7,600 images and is about 1.5GB in size.

### Approach
This problem and dataset appear to be well suited for a computer vision classification model. Models, generally a convolutional neural network, can breakdown the important components of images and be used to classify.

### Solutions
Training CNN models has been democratized through a few popular frameworks. [One can even train a NN using a web camera](https://beta.observablehq.com/@nsthorat/how-to-build-a-teachable-machine-with-tensorflow-js "TF js").

Image classification models can benefit from "transfer learning" which leverages pre-trained CNN models such as ResNet50, ImageNet, or InceptionV3. This allows users to build classification models using smaller datasets.

I am hoping to make use of the lower level layers (e.g. edges, lines, location imortance) of these pre-trained models.

I have had success using Keras, which is a deep learning framework that lives on top of TensorFlow. 
* [Keras Image Classifier Example #1](https://www.pyimagesearch.com/2018/09/10/keras-tutorial-how-to-get-started-with-keras-deep-learning-and-python/ "Keras 1")
* [Keras Image Classifier Example #2](https://github.com/risenW/medium_tutorial_notebooks/blob/master/dogs-vs-cats-keras-implementation.ipynb "Keras 2")

[PyTorch is another popular deep learning framework](https://github.com/WillKoehrsen/pytorch_challenge/blob/master/Transfer%20Learning%20in%20PyTorch.ipynb "PyTorch").

Python will be the easiest to collaborate / configure in a cloud service. (However, I prefer using R, which has a Keras library).

### Challenges
[As noted in this Keras tutorial](http://manning-content.s3.amazonaws.com/download/9/9a3b0d8-e651-4239-8c4f-94267be64fee/SampleCh03.pdf "RKeras"), training a new image classification model requires a lot of compute power. This means I need to use a cloud service with a GPU or TPU kernel

*HERE IS WHERE I NEED HELP*

I have not been able to figure out a place to train this model (which will also require me to store the image files).

[There are many deep learning cloud services](https://towardsdatascience.com/maximize-your-gpu-dollars-a9133f4e546a "GPUs"). I don't have a preference. I can spend *some* money but not more than $20-$30. I am thinking [GCP](https://cloud.google.com/solutions/running-distributed-tensorflow-on-compute-engine "GCP") or [AWS](https://aws.amazon.com/sagemaker/ "AWS").

[TensorFlow Hub might also provide something akin to this](https://www.tensorflow.org/hub/ "TFHub").

Can you setup a workspace on a deep learning cloud service?
