# Kaggle-Challenge
Regression with a Mohs Hardness Dataset

This repository is an attempt to predict the Mohs hardness of a mineral based off of it's properties. The Mohs hardness scale measures a mineral's resistance to scratching.  
---
## Overview
### What is the challenge?  
Build a model to predict the hardness of unidentified minerals, the only qualities known are provided  
### My approach
Building two regression models, comparing performance and choosing best model to make predictions
### Performance  
My best model had a mean squared error of 1.216.
---  
## Data  
- File type:
  - Input: train.csv (10407, 13)
  - Input: test.csv (6939, 12)
  - Output: submission.csv (
- Explaination of properties:
  - allelectrons_Total: Total number of electrons
  - density_Total: Total elemental density
  - allelectrons_Average: Atomic average number of electrons
  - val_e_Average: Atomic average number of valence electrons
  - atomicweight_Average: Atomic average atomic weight
  - ionenergy_Average: Atomic average frst IE
  - el_neg_chi_Average: Atomic average Pauling electronegativity of the most common oxidation state
  - R_vdw_element_Average: Atomic average van der Waals atomic radius
  - R_cov_element_Average: Atomic average covalent atomic radius
  - zaratio_Average: Atomic average atomic number to mass number ratio
  - density_Average: Atomic average elemental density
  - Hardness: Mohs hardness (target)
## Preprocessing and Cleanup
  - I dropped 'Hardness' from training data, and checked for missing values using IMPUTER, found none.
## Data Visualization 
A heatmap that shows correlation    
![image](https://github.com/hlnbkr/Kaggle-Challenge/assets/113190917/83de7c74-ebff-4f87-9afb-6736d09043b6)

Scatterplots comparing electrons to atomic weight, atomic radius, density, and van der Walls atomic radius  
![image](https://github.com/hlnbkr/Kaggle-Challenge/assets/113190917/5661edee-dc24-486e-90f0-ae9c7c9671d4)

## Problem Formulation
- Using RandomForestRegressor from sklearn.ensemble that estimates the data with classifiying decision trees on the training dataset, I used 50.
- Using LGBMRegressor from lightgbm which is a gradient boosting model, I used 200 estimate
- Both are simple and straightforward models

## Training  
- Because of the simplicities of the models, the training was lightweight
- Utilized the sklearn module for .fit of data
- Had trouble scaling the data output
- Used StandardScaler for this project, not successful

## Performance  
- Comparing the RandomForestRegressor and LGBMRegressor
- Used the Mean Squared Error to evaluate models, simplicity 
  Model Performance Metrics
![image](https://github.com/hlnbkr/Kaggle-Challenge/assets/113190917/6e67d171-c8d8-4094-8ee8-2c8cae1427f6)

## Conclusion
LGBMRegressor had a better performance than RandomForestRegressor
- More needs to be done to get the model running at its best

## Future Work
In the future I would like to try handling images instead of a regular dataset
