# A Beginner's Guide to recent Artificial Intelligence Research Papers
*This guide is intended to introduce students of the field to various recent developments that I find particularly cool, relevant or interesting. Rather than provide an in-depth evaluation and analysis of the theories discussed, this guide simply provides a high-level overview suitable for gaining an intuitive understanding of the papers.*


## 2019
* **January - [3D Pose Estimation](https://arxiv.org/pdf/1901.03798.pdf)**

A pose estimator takes a video as an input, and outputs a figure that corresponds to the pose of the human individuals present in the video. 

Current difficulties with creating a reliable and real-time 3D pose estimator include the fact that there is little training data, alongside the fact that occlusions must be taken to account. For example, if a particular body part is blocked from view, a pose estimator must still be able to infer its position from the position of the rest of the body.

This model outperforms all present models as it creates both 2D and 3D representations of the poses. It uses an initial 2D pose estimation, and then utilises a neural network that converts this 2D estimation into a 3D form. It then uses a 3D-to-2D neural network network to convert the pose back into 2D form, which helps to refine the intermediate 3D pose prediction via a self-supervised correction mechanism that can detect the accuracy of the first 2D-to-3D neural network. 

The networks allows for the pose estimation to be obtained in about 50 milliseconds, which is nearly 20 frames per second. This is close to real-time, and is suitable for many of the applications of pose estimation.

## 2018
* **April - [ProGanSR](https://arxiv.org/pdf/1804.02900.pdf)**

To acheive super-resolution, which allows the conversion of low-resolution images to higher-resolution ones, this paper recommends improving the image resolutions through a progressive method. It takes several intermediate steps where the image produced is slightly better than the predecessor, a known as 'curriculum learning'. 

The paper  uses a GAN rather than simply a CNN. Compared to state-of-the-art models, the images produced using the method proposed in this paper are comprehended with a slightly lower accuracy, however they are produced at 5 times the speed.


* **June - [RF-Pose](http://rfpose.csail.mit.edu/)**

The paper provides accurate human pose estimation through walls and occlusions. It leverages the fact that wireless signals in the WiFi frequencies traverse walls and reflect off the human body, and uses a deep neural network approach that parses such radio signals to estimate 2D poses. The pose estimation works well regardless of the lighting conditions, and can also detect multiple humans. 

In the network, there is a teacher network that looks at the colour image of the wall, and predicts the pose that the human is in. There is also a student network that has the signal as an input, and it learns what the different distributions mean, and how they relate to different human positions and poses. The teacher network shows the student network the correct results, and the student learns how to produce them from radio signals instead of images.

Besides being used for motion capture in interactive video games, as well as helping create special effects for movies, pose estimation can also be used to help detect issues with a patient’s posture, track the activity of animals, understanding sign language and pedestrian activity in self-driving cars. 

* **July - [Benchmarking Neural Network Robustness to Corruption & Perturbations](https://arxiv.org/pdf/1807.01697.pdf)**

This paper underlines a method to evaluate the performance of Image Classifiers in terms of their ability to withstand corruptions and perturbations. It creates two datasets - ImageNet-C (for corruptions) and ImageNet-P (for petrurbations) - which help test the robustness of Image Classifiers to such variations, which are common in real-life scenarios.

In the context of images, a corruption describes a modification to a base image through distorting its details. The paper utilises 15 different corruption functions on ImageNet mages, each of 5 levels of severity. These corruption functions describe methods including Gaussian Noise, the addition of snow and pixelation.

A perturbation describes the distorting of images by varying its appearance through transformative methods. The paper utilises 8 different perturbation functions on ImageNet images, including zoom, tilt and translation.

Testing the Classifier with images obtained from the ImageNet-C and ImageNet-P datasets, the paper creates a robustness score regarding a its robustness to both corruption and perturbation by averaging its accuracy over all functions of each type and over all levels of severity.

* **July - [Phrank](https://www.nature.com/articles/s41436-018-0072-y)**

The algorithm produced automates the most labor-intensive part of genetic diagnosis, that of matching a patient’s genetic sequence and symptoms to a disease described in the scientific literature. Without computer help, this match-up process takes 20 to 40 hours per patient - the process involves the expert looking at a list of around 100 of the patient’s suspicious-looking mutations, making an educated guess about which one might cause disease, checking  scientific literature, and then moving on to the next one. The algorithm developed by Bejerano’s team cuts the time needed by 90 percent. 

The algorithm’s name, Phrank, a mashup of “phenotype” and “rank,” gives a hint of how it works: it compares a patient’s symptoms and gene data to a medical-literature knowledge base, and then simply generates a ranked list of which rare genetic diseases are most likely to be responsible for the symptoms. Phrank, on average, ranked the true diagnosis 4th on the list of potential diagnoses it generated. 


* **December - [Style-Based Generator](https://arxiv.org/pdf/1812.04948.pdf)**

This research paper, authored by scientists at processor and graphics card company Nvidia, demonstrates the potential of an alternative generator architecture for generative adversarial networks that borrows from style transfer literature. It allows for specific customisation and control over features within a human face. It has the potential to be applied to other fields, and has thus far been tested successfully on cars and rooms. The generator has three main features:
  - It can combine different aspects of images. For example, if one wished to overlay the gender of one face with the face of another, the generator can do so. The aspects that can be transferred include gender, hair length, pose and the presence of glasses.
  - The parameters can be controlled one by one without modifying the core content of an image. For example, the presence of a stubble can be modified.
  - It can perform interpolation. This means that if we have two images A and B, the generator can create intermediate images that map one to another. It can even change the gender in the process. All intermediate images look real too.
  
  
## 2019

* **September - [Deep Feature Consistent Deep Image Transformations (DFC-DIT)](https://arxiv.org/pdf/1707.09482.pdf)**

Say you need to downscale an image of yours without reducing the accuracy of the main features, or if you wished to remove RGB colours from an image, or if you display an image of high dynamic range on a screen that doesn’t support the range. Though there are hundreds of existing structures that do these, this paper describes a method that does these exceptionally well in comparison to current methods. 

The paper suggests a Deep Feature Consistent Deep Image Transformation (DFC-DIT) framework. It utilises a Convolutional Neural Network (CNN) that produces three outputs for an input image - a downscaled version, a decolorised version and a HDR tone mapped version. It also uses another pretrained and fixed deep CNN that employs the deep feature consistency principle - this ensures that all main features are preserved in the image. 
