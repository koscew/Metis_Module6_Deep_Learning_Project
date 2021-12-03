# Human Recognition Project
Chien Yuan Chang

## Abstract
The goal of this project was to use images with and without humans to build a neural network model to recognize whether an image contains humans. The security system can use this model to recognize humans and/or count the number of individuals in a space.

I downloaded and mixed various datasets of images on Kaggle. The final dataset contained a total of 7,424 images of 3,712 images with humans and 3,712 images without humans. 58.6% of data were used for the training while 20.7% of data were reserved for the validation and another 20.7% of data were reserved for the final testing.

I used Random Forest Classifier to build the baseline model. Then, I used image data generator and image augmentation as preprocessing to build my own Convolutional Neural Network model and also tried transfer learning with MobileNetV2, VGG16 and InceptionV3 and ran the models on Google Colab.

The transfer learning model with MobileNetV2 had the best performance. I evaluated the F1-score and decided to use 59% as the threshold for the best F1-score and better accuracies of both training (98.48%) and validation data (95.77%). The accuracy on the test data was 96.09%.

## Design

Smart Doorbells and security cameras are common and popular. At first it only had a motion detection feature, and anything like humans, cars and animals passing could trigger the alert. A human recognition model can help alert only when humans are approaching. Some latest smart doorbells already had facial recognition features.

A neural network model to recognize whether an image contains humans can also be used in counting crowds to help control the maximum occupancy. Especially during the pandemic, there would be more restrictions on occupancy. It will be more efficient to let the security system and machine learning model count the crowd. 

## Data

I downloaded and mixed datasets of images on Kaggle. I used the images of three datasets of human recognition([1](https://www.kaggle.com/jithinnambiarj/human-activity-detection-dataset)/[2](https://www.kaggle.com/siddhrath/human-or-thing-classifier)/[3](https://www.kaggle.com/constantinwerner/human-detection-dataset)), images of waste in [garbage classification dataset](https://www.kaggle.com/asdasdasasdas/garbage-classification), images of furniture in [furniture dataset](https://www.kaggle.com/lasaljaywardena/furniture-images-dataset), and images of animals in [10 animals dataset](https://www.kaggle.com/alessiocorrado99/animals10). The final dataset contained a total of 7,424 images of 3,712 images with humans and 3,712 images without humans. 4,352 images (58.6%) were used for the training while 1,536 images (20.7%) were reserved for the validation and another 1,536 images (20.7%) were reserved for the final testing. The image data generator and the image augmentation were used as preprocessing.

## Algorithms

***Image augmentation***

* Images were flowed from directories by the image data generator.
* All images were resized to 224 by 224.
* All images were rescale to 1/255.
* Horizontal flip was used for training data.
* Rotation, width shift, height shift, shear, and zoom were tried but not used for the final model.

***Models***

Random Forest, Convolutional Neural Networks from scratch, Transfer Learning with MobileNetV2, VGG16 and InceptionV3 were used before settling on the Transfer Learning model with MobileNetV2 which had the best performance.

Model/Architecture|Validation Accuracy
---:|---:|---:
Transfer Learning with MobileNetV2|0.9544
Transfer Learning with VGG16|0.9173
Random Forest|0.8053
Convolutional Neural Networks from scratch|0.7598
Transfer Learning with InceptionV3|0.7565


***Architecture***

- Input: 224 (height) x 224 (width) x 3 (channels) 
- Transfer Learning(MobileNetV2): 7 x 7 x 1280 (outputs)
- Flatten
- Dense: 1024 fully connected neurons with ReLU activation
- Dropout: 0.05
- Dense: 1024 fully connected neurons with ReLU activation
- Dropout: 0.05
- Dense: 512 fully connected neurons with ReLU activation
- Output: Binary with sigmoid activation

***Model Evaluation***

After evaluating the F1-score, the threshold at 59% had the best F1-score and F0.5-score and better accuracies of both training and validation data. Therefore, 59% was used for the final threshold. 

Metrics|Training Data|Validation Data
---:|---:|---:
Loss|0.0547|0.1210
Accuracy at 50% threshold|0.9821|0.9544
F1-score at 50% threshold|0.9832|0.9547
Precision at 50% threshold|0.9826|0.9486
Recall at 50% threshold|0.9839|0.9609
Accuracy at 59% threshold|0.9848|0.9577
F1-score at 59% threshold|0.9848|0.9577
Precision at 59% threshold|0.9871|0.9583
Recall at 59% threshold|0.9825|0.9570

**Best F2-score at 34% threshold*

***Holdout***

The entire dataset of 7,424 images was split into 58.6%/20.7%/20.7% train/validation/holdout. Predictions on the 20.7% holdout were limited to the very end, so this split was only used and scores seen just once.

   - Accuracy: 0.9609
   - F1-score: 0.9610
   - Precision: 0.9585  
   - Recall: 0.9635


## Tools
- Python Pandas and Numpy for data engineering
- Python Pillow for image preprocessing
- Python Scikit-learn for baseline model
- Google Colab for GPU boosting
- Python Keras and TensorFlow for neural network model
- Python Matplotlib and Python Seaborn for data visualization


## Communication
In addition to [the slides of the final presentation](final_presentation.pdf), [charts](images/), [codes](codes/), and this written description, the findings will also be posted on [my personal blog](https://koscew.github.io/) in the future.