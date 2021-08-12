# machine-learning-challenge
Week 21 Machine Learning Homework

> Created by Dale Currigan  
> August 2021  
  
![ML](/exoplanets.jpg)  

## Table of contents  
* [Project Intro](#Project-Intro)  
* [Project Structure](#Project-Structure)  
* [Setup](#Setup)  
* [Design](#Design) 
* [Sources](#Sources)  
* [Contributors](#Contributors)  
* [Status](#Status)  

# Project Intro
This project involved creating machine learning models capable of classifying possible exoplanets into one of three categores - 'CONFIRMED', 'FALSE POSITIVE', or 'CANDIDATE' - based upon data from the <a href="https://www.kaggle.com/nasa/kepler-exoplanet-search-results">NASA Kepler Space Telescope</a>. The briefing for the project was as follows: 
  
*Over a period of nine years in deep space, the NASA Kepler space telescope has been out on a planet-hunting mission to discover hidden planets outside of our solar system.
To help process this data, you will create machine learning models capable of classifying candidate exoplanets from the raw dataset.*  

  
# Project Structure  
```
machine-learning-challenge   
|  
|__ ipynb_checkpoints/                      # Directory for notebook savepoints
|__ hp_dir/                                 # Directory for neural network hyperparameter tuning  
|
|__ README.md                               # This file
|__ exoplanets.jpg                          # images files for the readme
|__ matrix1.png
|__ matrix2.png
|                           
|__ model_1 - Decision_Tree.ipynb 
|__ model_2 - Deep Learning.ipynb           # Directory for css stylesheets                             
|__ model_3 - SVM.ipynb                               
|__ model_4 - KNN.ipynb                                 
|                                 
|__ model_2 - Deep Learning.ipynb           # The best performing model
|                             
|   
``` 
  
# Setup 
  
* Each model has been saved as individual jupyter notebook 
* The final, best performing model was the deep learning neural network. This has been saved in h5 file format
* This can be loaded by runnning the final cell in the deep learning notebook, or with the following code:  

```
# Load the model
from tensorflow.keras.models import load_model
model = load_model("Model 2 - Deep_learning.h5")
```   
   

# Design  
Four models were trialled for this project:  
1. Decision tree  
2. Deep learning neural network  
3. Support vector machine  
4. k-nearest neighbor  
  
<strong>Pre-processing</strong>  
Basic data cleaning was first performed with removal of Nan and null values  
Definitions for the columns headers was sourced from <a href="https://exoplanetarchive.ipac.caltech.edu/docs/API_kepcandidate_columns.html">NASA exoplanet archive</a>  
  
All columns relating to level of uncertainty (error) were removed as these would relate only to the individual feature and would be not relevant to classification.  

'koi_disposition' was used for *y* and consisted of three possible options - 'CONFIRMED', 'FALSE POSITIVE', or 'CANDIDATE'. All other features were inititially used for *X*.
  
*X* and *y* values were split into training and testing sets using SKlearns train_test_split. *X* values were then scaled using a MinMaxScaler. *y*-values were converted from categorical to numerical using label encoder. For the neural network keras to_categorical was additionally used.  

<strong>Feature Selection</strong>  
To optimise feature selection various methods were trialled. 

For the decision tree model feature importance was ranked. The model was re-run with after eliminating of models of low contribution to the model, but this this decreased the model score.  

For the deep learning model recursive feature elimination was used to find the optimal features to include in the model. 
  
<strong>Hyperparameter Tuning</strong>  

  
  
<strong>Assumptions</strong>  
For the deep learning model the 2 hidden layers assumed a rectified linear unit activation function, whilst the output layer assumed a sigmoid function
 
  
# Model Performance
|No|Model|Accuracy|Precision|Recall|F1-score|
|-|-|-|-|-|-|
|1|Decision Tree                |0.89|0.89|0.89|0.89|
|2|Deep Learning                |0.90|0.90|0.90|0.90|
|3|Support Vector Machine       |0.80|0.80|0.80|0.80|
|4|k Nearest Neighbor           |0.81|0.81|0.81|0.81|  
  
![ML](/matrix1.png)   ![ML](/matrix2.png)   
Comparative confusion matrices for the best two performing final models, decision tree (left) and deep learning neural network (right) 

   
# Contributors  
Dale Currigan  
[@dcurrigan](https://github.com/dcurrigan)  
<dcurrigan@gmail.com>


## Status
Project is: 
````diff 
+ Completed
````

