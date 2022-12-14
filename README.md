# Object_detection
2D object detection

VGG Net, Res Net, Inception
Fast RCNN
SSD,YOLOv4


3D object detection can be done using 2D object detection+ Depth estimation using sterio vision

A very good resource to refer concepts of deep learning http://cs231n.stanford.edu/schedule.html


Multiple Object tracking is done using YOLO and DeepSORT(Simple Online Realtime Tracking) 
(Detection, prediction, association)
1. Perform object detection using YOLOV4
2. Deep SORT (Deep sort is extension of sort algorithm)
    --Kalman filtering: Process the correlation frame by frame
    --Hungarian Algorithm: correlation measurement
    --CNN Networks: Training and feature extraction
    
Good resource to implement Tracking is https://github.com/mikel-brostrom/Yolov5_StrongSORT_OSNet

YOLOv7 which was launched recently surpassed all the earlier known object detector in speed and accuracy.
Good medium article to implement perception problems is:
https://medium.com/@shahrullo/visual-perception-for-self-driving-cars-bb500f8c6adc



# Perception for Self Driving Cars
Perception proble for self driving cars is to get data from sensors, understand the scene and pass the information to planning module
Inorder to understand the perception architecture, we look how Tesla is solving this problem.

Earlier architecture is hydra nets to detect objects, lane lines, depth and segmentation masks from each camera feed.
While this approach increased the computation efficiency, it is lacking the spacial and time awareness. To solve the issue, Tesla built an unique architecture.

Camera feed from all the 8 cameras are read and a vector space is generated. This vector space is a 3D world representation of surrounding around the car.
Object detection, tracking, segmentation, depth estimation, time awareness, lane detection, object detection is performed in vector space. 
But standard data sets for creating and understanding vector space are not available. So tesla created the on their own.

Occupancy network.



Choice of loss function varies depending on the problem. Loss function calculates deviation between predicted and actual values whereas cost function calculates average fo the deviation across the training dataset.

Using inbuilt python function significantly increases the speed of computation than using explicit for loops in the code.
Derivative of ReLU activation is either 0(for negative input) or 1(for positive value). Hence speed of execution is faster. 
Tanh activation is superior than sigmoid function.
Choice of loss function depends on problem. Whether Classification or regression. If classification number of classes. 
Parameters while a DNN are weights and biases.
Hyperparameters learning rate, Number of iterations, number of hidden layers, number of units in each layer, choice of activation layer, momentum, mini batch size, regularization parameters, etc

Model which underfits the data is said to be having high bias and model which ovefits is said to be having high variance.
Looking at training error model bias can be determined and validation error is used to estimate the model variance.

To reduce bias, increase the size of dataset, increase the model and train for longer
To reduce variance, use regularization.

Regularization prevents overfitting.
L2 regularization is penalising the weights with L2 norm.
Dropout regularization
Other regularization techniques are data augmentation(Rotation, cropping, distortion), Early stopping etc


Normalization:
Normalizing the input data makes the learning process faster.
Vanishing or exploding gradient can be partially solved by careful initialization of weights.

While choosing the mini-batch size, select number which can be represented as a power of 2 ( eg: 64,128,256,512 etc). This helps in faster training.
And mini batch size should fit in the CP/GPU memory
Adam Optimization is the combination of momentum and rmsprop algorithms.
Training(learning) the network is nothing but optimizing the parameters(weights and biases).
1 Epoch is when network sees the entire training set once.  

