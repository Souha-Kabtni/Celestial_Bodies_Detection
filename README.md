![image](https://github.com/Souha-Kabtni/Celestial_Bodies_Detection/assets/133057039/7d0e9e30-8584-4bb6-b65c-a803b34c48f3)


# Celestial_Bodies_Detection

Souha Kabtni

## Predicting Celestial Bodies According to their Spectral Properties

The categorization of stars, galaxies, and quasars based on their spectral properties is a crucial concept in the field of Astronomy. By dividing stars into different categories based on factors such as their temperature, luminosity, and chemical composition, we can gain insight into their physical properties and evolutionary stages. Therefore, in this project, I will employ several classification algorithms to help classify observations of space to either stars, galaxies, or quasars based on their observed properties.


Data on Celestial Objects from the Sloan Digital Sky Survey - Data Release 18. Click [here](https://docs.google.com/spreadsheets/d/1r0O_8CsKY4KMKlf2aHoOIxbXElmb_fVxeNreNhfS8ms/edit#gid=2032989002) to download the dataset.

For this dataset, there were ``` 100,000 rows```  and ``` 43 columns```.

## Data Dictionary

![image](https://github.com/Souha-Kabtni/Celestial_Bodies_Detection/assets/133057039/a24499b6-73c8-4804-968f-c3823eb9f85b)


## To prepare this data, the data was cleaned, and the following processes were performed:

### Exploratory Data Analysis

    - A heatmap was visualized to display the feature/feature and feature/target relationships. 
    - Distplots were visualized for each feature/target relationship. 
    - This gave a good baseline for univariate EDA.

### Explanatory Data Analysis

    - 1 line plot and 1 scatterpolar were chosen.
    - The Scatter polar was chosen to showcase the Top 15 Most Important Features to the Target. 
    - The line plot was chosen to show how the 'Redshift' feature helps differentiate between the 3 celestial objects. 

### Explanatory Visuals

![image](https://github.com/Souha-Kabtni/Celestial_Bodies_Detection/assets/133057039/25cfcd90-7d58-4280-8d5b-30e35e0c079b)


This scatter polar, clearly shows that redshift is the most important feature that helped classify the data. So this is the best in terms of splitting ability. *PetroR50_i, PetroR50_g, PetroR50_z, PetroR50_u, and PetroR50_r are the following most important features that impact the distinguishing between all 3 celestial bodies. (*PetroR50_(Photometric band): These parameters are important for characterizing the sizes of objects in the SDSS data and how the sizes of the objects vary at different wavelengths)

![image](https://github.com/Souha-Kabtni/Celestial_Bodies_Detection/assets/133057039/f7aee84c-39b4-426a-9ecc-97d1019d4268)

The line plot shows that QSO is by far the most distant celestial object for it is the most redshifted. Both GALAXY and STAR are not that distant from the Earth with close Redshift values.

## Pre-processing:

Having performed all data cleaning steps, my data set had to be scaled to avoid exploding weights. Besides, PCA was applied to reduce the feature space I am working with (I started with 42 features, and with PCA applied, I ended up with 23 features that helped capture 99% of the variance in the Target class variable. 

## Machine Learning Using the Following Models:

    - k-nearest neighbors (KNN) Algorithm
    - Random Forest Classifier Algorithm
    - Logistic Regression Algorithm
    - XGBoost Algorithm

## Deep Learning Using:
    - Sequential model


## Models Evaluated & Results

+ Below are the best sores delivered by each model (Defaulted or Tunned)

| Model (Testing Set)  | Accuracy Score | Recall Scores `GALAXY` |Recall Scores `QSO`|Recall Scores `STAR`|AUC Scores `GALAXY`|AUC Scores `QSO`|AUC Scores `STAR`| Wall time (prediction time)|
| :---         |     :---:      |          ---: |          ---: |          ---: |          ---: |          ---: |          ---: |          ---: |
| k-nearest neighbors (KNN) Algorithm | 0.98 | 0.97 | 0.98 | 0.99 | 0.99 | 1.00 | 1.00 | 1min 36s |
| Random Forest Classifier Algorithm | 0.98 | 0.99 | 0.96 | 0.99 | 1.00 | 1.00 | 1.00 | 2.19 s |
| Logistic Regression Algorithm | 0.98 | 0.98 | 0.96 | 1.00 | 0.99 | 1.00 | 1.00 | 50.7 ms |
| XGBoost Algorithm | 0.99 | 0.98 | 0.96 | 1.00 | 0.99 | 1.00 | 1.00 | 73.1 ms |
| Sequential model | 0.99 | 0.98 | 0.98 | 1.00 | - | - | - | 2.69 s |


All trained models delivered great results with high Accuracy scores. My final model was chosen on the basis of the best-delivered AUC results as well as the less time the model took to make its predictions. In this vein, the XGBoost Algorithm, which delivered an accuracy score of 0.98 and predicted the values of the test set in only 73.1 ms was chosen as my final model.

## Strengths

Since no cleaning was involved (no missing values, no duplicates, no inconsistent data, …), all the time was dedicated to the Modelling phase. Besides, all created models are accurate enough to classify these celestial objects.

## Limitations & Next Steps

The ratio of the data is drastic: 52343 rows (52.343%) are classified as galaxies, 37232 rows (37.232%) are classified as stars, and only 10425 rows (10.425%) as quasars (although SMOTE was used to handle the imbalanced classes, it still "fail[s] to reach high levels of recall while creating undue complexity for the machine-learning pipeline." (From Medium Article entitled: Stop Using SMOTE to Treat Class Imbalance). So, other techniques might be used to better address class imbalance.

## Recommendations

+ All created models can be used in the future to classify these celestial objects with great accuracy;
+ Although delivered the best results, XGBoost was not tuned. There is still potential for XGBoost to deliver more accurate predictions.
+ Deep Learning models were not 'heavily' tuned, and if so, better results might be expected;
+ As there is data about the camera as well, we can perform analysis on them as well;
+ Some feature engineering might be involved.

## For Further Information
For any additional questions, please contact:

Souha Kabtni
souha.kabtni.data@gmail.com

