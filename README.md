# RD-Data-Takehome-Derek-Deming
Technical interview for Reality Defenders - Data Engineer Take Home 

### Instructions:
1. Install the required libraries using pip:
        **pip install -r requirements.txt**
2. There is also a project.yaml file which contains dependencies, environemnt, libraries, and python version. Run the following command to execute yaml file: 
        **pipenv run invoke -f projects.yaml**

3. Every question has its own folder and within each folder there is going to be a few files depending on the question: 
+ ipynb file - This will contain the code needed for the question. I used jupyter notebook for simplicity 
+ markdown file - This contains explanations to the questions. Some questions will have both a ipynb and markdown to explain both. 
+ dataset folder - This folder contains the subset of images used for the project 

4. Run through each question folder in sequential order to run from end-to-end

### Explanation of each folder: 
**Question_01**: 
1. Contains the following: 
+ real_and_fake_face folder (large dataset used for creating a subset of 100+ images)
+ dataset folder (the actual dataset used for this project) 
+ dataset.zip (zip folder of the dataset) 
+ design_build.ipynb (code used to build the dataset). The dataset was taken from kaggle and then altered to create a subset of the original data 
+ explanations.md - contains explanations to the questions 

**Question_02**: 
1. Contains the following: 
+ explanations.md - contains explanations to the questions 

**Question_03_v1**: 
1. Contains the following: 
+ deep_learning.ipynb - code used for the question 
+ explanations.md - contains explanations to the questions 
+ my_model.h5 - saved the model 
+ predictions.csv - this is the predictions for the model on the dataset provided by RD


**Question_03_v2**: This was only done to continue to test out the models - disregard this as the data augmentation caused overfitting and some issues that could not be visited during the time alotted 
**THIS SHOULD NOT BE USED AS THE PRIMARY ANSWER FOR NUMBER 3 - THIS WAS JUST EXTRA CODE THAT I FIGURED I WOULD INCLUDE AS IT WAS TECHNICALLY PART OF THIS**
1. Contains the following: 
+ modeling_2.ipynb - code used for the question 
+ predictions.csv - this is the predictions for the model on the dataset provided by RD

**Question_04**: 
1. Contains the following: 
+ explanation.md



