# Detecting Weapon Objects by using one-stage object detection model

I have used Object Detection API and retrain [RetinaNet](https://arxiv.org/abs/1708.02002) model to spot weapon objects using just 4 training images.

RetinaNet is one of the best one-stage object detection models that has proven to work well with dense and small scale objects. For this reason, it has become a popular object detection model that we use with aerial and satellite imagery.

 

The model was introduced by Facebook AI Research to tackle the dense detection problem. It was needed to fill in for the imbalances and inconsistencies of the single-shot object detectors like YOLO and SSD while dealing with extreme foreground-background classes.

 
In essence, originial RetinaNet is a composite network composed of:

* Backbone Network (i.e. Bottom-up pathway + Top down a pathway with lateral 
connections eg. ResNet + FPN)

* Subnetwork for object Classification

* Subnetwork for object Regression

<img src='https://cdn.analyticsvidhya.com/wp-content/uploads/2020/08/image13-850x217.png' alt='model'>

First of all, I cloned the [Tensorflow Model Garden](https://github.com/tensorflow/models) and install the Tensorflow 2 [Object Detection API](https://github.com/tensorflow/models/tree/master/research/object_detection).

Next, I downloaded [RetinaNet](https://arxiv.org/abs/1708.02002) modle checkpoints and copied it inside the object detection directory. After this, I configured the model for this use case. I used **model_builder** to build the model according to the configurations that I have just downloaded and customized.

 Although I have just used 4 images for training, model performance to get the detection scores and bounding boxes to overlay in test images is so good. I saved each result in a results1 dictionary and the autograder used this to evaluate my results. Some test results: 

