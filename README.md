# A Microcontroller Implementation of A CNN Inference For Detecting Cardiac Arrhythmias

Heart diseases have one of the highest mortality rates in the world. In addition, the small number of specialists in this field and their limited geographical distribution make the detection and treatment of this type of disease entail high costs in terms of time, money, and human talent. Therefore, we implemented the inference of a convolutional neural network to detect cardiac arrhythmias in Teensy 4.1 microcontroller. This device has relevant characteristics in terms of portability, energy consumption, and memory. The neural network to implement is the SqueezeECG, which detects cardiac arrhythmias from ECG signals without preprocessing. It offers higher accuracy than the average cardiologist and has about 20 times fewer parameters than models of similar accuracy. Our results show accuracy, precision, recall, and F1 score values above 0.8. We achieved an inference time of 4205ms and latency of 8196ms at an operating frequency of 396MHz. The inference process required  813kB of Memory Flash and 750kB of Memory RAM.

## **Description of the files**
### *Model.ino*
This is the main project file. It contains the description of the CNN implementation. It describes each of the residual blocks that compose the model using the functions created. Each block is described layer by layer reusing the global variables to reduce the memory consumed. 
### *functions.h*
This header file contains the description of the functions for each layer of the CNN implementation. Each function emulates the behavior of its corresponding layer based on the operations it performs. 
### *model_parameters.h*
This header file contains the parameters of the CNN implemented. We used the progmem function to store them in the Flash Memory of the Microcontroller.
### *Matlab Files (.m)*
To generate the model_parameters.h file we use the rest of the files: write_parameters_matrix.m, write_parameters_vector.m and Open_h5.m. 
The first two are functions for Matlab that allow us to write the parameters in the format required. The Open_h5.m is the main file in Matlab. 
To generate the header file we need the name we want for it and the weights of the CNN in a .h5 file generated in Tensorflow after training the Network. 
By running the Open_h5.m we will obtain the header file for the implementation. 

## Operation Video
In the next video you will see a full description of the operation of our project. 

[![Alt text](https://img.youtube.com/vi/C8KOdEeG2JY/0.jpg)](https://youtu.be/C8KOdEeG2JY)

