## Human Recognition
###### Chien Yuan Chang

The goal of this project is to use images with and without human to build a neural network model to recognize whether an image contains human. The security system can use this model to recognize human and/or count the individuals in a space.

To start exploring this goal, I downloaded and mixed datasets of images on Kaggle. I used the images of three datasets of human recognition([1](https://www.kaggle.com/jithinnambiarj/human-activity-detection-dataset)/[2](https://www.kaggle.com/siddhrath/human-or-thing-classifier)/[3](https://www.kaggle.com/constantinwerner/human-detection-dataset)), images of waste in [garbage classification dataset](https://www.kaggle.com/asdasdasasdas/garbage-classification), images of furniture in [furniture dataset](https://www.kaggle.com/lasaljaywardena/furniture-images-dataset), and images of animals in [10 animals dataset](https://www.kaggle.com/alessiocorrado99/animals10). The final dataset contained total 7,424 images of 3,712 images with human and 3,712 images without human. 4,352 images (58.6%) were used for the training while 1,536 images (20.7%) were reserved for the validation and another 1,536 images (20.7%) were reserved for the final testing.

I used Random Forest Classifier to build the baseline model. The accuracy of training data was 99.98% while The accuracy of validation data was 80.53%. I also built a Convolutional Neural Network model with 77.23% accuracy of training data and 75.98% accuracy of validation data.

I will use image augmentation and transfer learning to build a Convolutional Neural Network classification model to improve the accuracy.
