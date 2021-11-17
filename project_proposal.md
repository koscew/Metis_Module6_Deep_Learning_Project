### Project Proposal of Deep Learning Project
Chien Yuan Chang
#### Question/need:
I am going to use images with and without human to build a neural network model to detect whether an image contains human. The security system can use this model to detect human and/or count the individuals in a space.

>* What is the framing question of your analysis, or the purpose of the model/system you plan to build?
>* Who benefits from exploring this question or building this model/system?

#### Data Description:
* Dataset: 
  * I downloaded and mixed three datasets on Kaggle. I used the images of control(images without human), standing and walking in [human activity dataset](https://www.kaggle.com/jithinnambiarj/human-activity-detection-dataset), images of things in [human or thing classifier dataset](https://www.kaggle.com/siddhrath/human-or-thing-classifier), and images of furniture in [furniture dataset](https://www.kaggle.com/lasaljaywardena/furniture-images-dataset) of images of waste, one .The final dataset contained 1024 images with human and 1024 images without human. 
 
>* What dataset(s) do you plan to use, and how will you obtain the data?
>* What is an individual sample/unit of analysis in this project? What characteristics/features do you expect to work with?
>* If modeling, what will you predict as your target?

#### Tools:
* Python Pandas and Numpy for data engineering
* Python Scikit-learn for baseline model
* Python Keras and TensorFlow for neural network model
* Other Python libraries or tools if needed

>* How do you intend to meet the tools requirement of the project? 
>* Are you planning in advance to need or use additional tools beyond those required?

#### MVP Goal:
* The baseline model

>* What would a minimum viable product (MVP) look like for this project?
