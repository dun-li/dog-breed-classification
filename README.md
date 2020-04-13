# dog-breed-classification

## Table of Contents

1. [Installation](#installation)
2. [Project Motivation](#motivation)
3. [File Descriptions](#file)
4. [Technical Details](#technical)
5. [Conclusions](#conclusions)
6. [Licensing and Acknowledgements](#licensing)

## Installation <a name="installation"></a>
The environment requirements are in the 'dog-mac.yml' file.<br>
In addition to the files in this repository, there are additional files needed to run the project. (These files are too big to be put in this repository.)
<br>
The file structure should be as follows:
> repository/  
&emsp;&emsp;bottleneck_features/  
&emsp;&emsp;&emsp;&emsp;DogVGG16Data.npz  
&emsp;&emsp;&emsp;&emsp;DogVGG19Data.npz  
&emsp;&emsp;dog_images/  
&emsp;&emsp;&emsp;&emsp;test/  
&emsp;&emsp;&emsp;&emsp;train/  
&emsp;&emsp;&emsp;&emsp;valid/  
&emsp;&emsp;haarcascades/  
&emsp;&emsp;&emsp;&emsp;haarcascade_frontalface_alt.xml  
&emsp;&emsp;images/  
&emsp;&emsp;lfw/  
&emsp;&emsp;saved_models/  
&emsp;&emsp;&emsp;&emsp;weights.best.from_scratch.hdf5  
&emsp;&emsp;&emsp;&emsp;weights.best.VGG16.hdf5  
&emsp;&emsp;&emsp;&emsp;weights.best.VGG19.hdf5  
&emsp;&emsp;dog-mac.yml  
&emsp;&emsp;extract_bottleneck_features.py  
&emsp;&emsp;dog_app.ipynb  
&emsp;&emsp;dog_app.html  
&emsp;&emsp;README.md  


## Project Motivation <a name="motivation"></a>
This project aims at developing an algorithm for a Dog Identification App. The algorithm should be able to tell whether an input image is a dog? a human? or neither.
If the input image is a dog, the algorithm should further tell which breed the dog belongs to.


## File Descriptions <a name="file"></a>
1. dog_app.ipynb: is the main file for the algorithm.
2. dog_app.html: is the html version of dog_app.ipynb.
3. extract_bottleneck_features.py: a helper function called by the dog_app.ipynb. 
4. dog-mac.yml: environment requirements file.
5. saved_models/: saved models during the training.
6. lfw/: human images for training and testing.
7. images/: testing images.
8. haarcascades/: pre-trained face detectors.
9. dog_images/: dog images for training and testing.
10. bottleneck_features/: bottleneck features from a pre-trained model.



## Technical details <a name="technical"></a>
The algorithm is implemented using transfer learning based on VGG-19. I added a global average pooling layer and a fully connected layer in the end. <br>
To save the running time of 'dog_app.ipynb', I turned the training off. If you would
like to retrain the model, you can change the parameter want_to_train_again to True. 


## Conclusions <a name="conclusions"></a>
1. Transfer learning is very powerful in image classification problems. 
2. With a simple transfer learning model, the testing accuracy for dog breed classification among 133 classes is already higher than 60%!
3. The developed algorithm can tell the difference between human and dog with nearly 100% accuracy. 

More details of this analysis can be found [here](https://medium.com/@lidun.cn/dog-breed-classification-based-on-transfer-learning-fc5fcd708c71).

## Licensing and Acknowledgements <a name="Licensing"></a>
Thanks Udacity for providing the dataset. The code in this repository is released under the MIT license. 