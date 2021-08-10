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
This project involved creating machine learning models capable of classifying possible exoplanets into one of three categores - 'CONFIRMED', 'FALSE POSITIVE', or 'CANDIDATE' - based upon data from the <a href="https://www.kaggle.com/nasa/kepler-exoplanet-search-results>NASA Kepler Space Telescope</a>. The briefing for the project was as follows: 
  
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
|__ model_2 - Deep Learning.ipynb           # The final model
|                             
|   
``` 
  
# Setup 
  
* The site is can be accessed at: https://dcurrigan.github.io/D3-challenge/
* The html for the site is all contained in index.html
* All styles are contained within static/css/D3style.css and style.css
* The javascript code enabling the functionality of the site is can be found within static/js/app.js
* The base dataset is found within data.csv   

# Design 
I've created an interactive web visualisation using D3 to explore the US Census Bureau data. <a href="https://data.census.gov/cedsci/">US Census Bureau data</a>. An interactive scatter plot has been generated with the data, allowing the user to investigate the data further by changing axes or the colour scale for the chart (see below).  
  
![D3](/Images/d3.gif)  
  
  
Example code sourced <a href="https://bl.ocks.org/starcalibre/6cccfa843ed254aa0a0d">here</a> provided the basis for the colour scaling and legend. The data points are coloured based upon the scale generated with scaleQuantize(), which allows scaling of a numerical value in the domain to a string (the colour hex value) in the range.    
  
**Example Code:** Creating a colour scale 
```
  function colour_scaler(data) {
    return d3.scaleQuantize()
      .domain([(d3.min(censusData, d => d[data])), (d3.max(censusData, d => d[data]))])  
      .range(['#E7F1D7', '#D0E7BD', '#B2DDA3', '#8FD28A', '#71C67B', '#59BA76', '#41ae76', '#379A7C', '#2E857E', '#256770', '#1D465B'])

  };
```
  
  
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

