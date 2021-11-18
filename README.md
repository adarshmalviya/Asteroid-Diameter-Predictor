<div align="center">

## 🚀 Problem Statement 💡 :

### Predict the correct diameter of the asteroids from the given datasets. 🌌

<div align="center">

| Variable Name | Description |
|----|----|
| a | semi-major axis[au] |
| e | eccentricity|
| i | inclination wrt x-y ecliptic plane [deg] |
| om | longitude of the ascending node |
| w | argument of perihelion |
| q | perihelion distance [au] |
| ad | aphelion distance [au] |
| per_y | orbital period [years] |
| data_arc | data arc-span [d] |
| condition_code | orbit condition code |
| n_obs_use | number of observations used |
| H | absolute magnitude parameter |
| diameter | diameter of asteroid [km] |
| extent | object bi or tri-axial ellipsoid dimensions [km] |
| albedo | geometric albedo |
| rot_per | standard gravitational parameter [m×Gm×G] |
| bv | color index B-V magnitude difference |
| ub | color index U-B magnitude difference |
| IR |color index I-R magnitude difference |
| spec_B | spectral taxonomic type (SMASSII) |
| spec_T | spectral taxonomic type (Tholen) |
| neo | near earth object |
| pha | physically hazardous asteroid |
| moid | earth minimum orbit intersection distance [au] |

 ##  🚀 **Dataset** 👩‍💻 **:**
 [Click Here for the Dataset](https://drive.google.com/drive/folders/16nMEa69FpomZQ0xy8ffQz6egJnG6edus?usp=sharing) 
 
 ## 👨🏻‍💻 Solution 💯
 
<div align="center">

### ✅ Basic Operations 💯
  
</div>
<div align="center">
  
#### File Name -> Feature_Engineering_and_EDA.ipynb

</div>

<div align="center">
  Imported Necessary Liberaries, Imported Dataset, Checked for shape of dataset, Finding the Information about datatypes of features, Spliting the features accouring to their datatype.
 </div>

<div align="center">

### ✅ Feature Engineering and Exploratorty Data Analysis 💯

</div>
<div align="center">
  
#### File Name -> Feature_Engineering_and_EDA.ipynb

</div>

<div align="center">
  
  <div>
    1. Univeriate Analysis
  </div>
  <div>
  a) On Numeric Data
  </div>
  Finding the mean, standard deviation, 25th percentile, 75th percentile, etc
  <div>
  b) On Categorical Data
  </div> 
  Made a frequency graph of variables and concluded its outcome
  
  
  <div>
    <br>
    2. Biveriate Analysis
  </div>
  <div>
  a) On Numeric Data
  </div>
  <div>
  Finding Correlation between features using heatmap and some functions 
  </div>
  Outcome : 4 Features are found to be heavily correlated with pearson correlation coeffcient greater then 0.97 or less the -0.97
   <div>
  b) On Categorical Data
  </div>
  <div>
  Performed Chi-Square Test on crosstab for finding out the relationship between the features
  </div>
  Outcome : Many Features have found to be related with p-value less than 0.05 (95% confidence)
  
  
  <div>
    <br>
    3. Handeling Missing Values
  </div>
    <div>
  a) On Categorical Data
  </div>
  Found the percentage of NaN values for each feature. Eliminated those features whose NaN values are greater then Non-NaN values and filled the rest with Mode of Data. 
  <div>
  b) On Numeric Data
  </div>
  Found the percentage of NaN values for each feature. Eliminated those features whose NaN values are greater then Non-NaN values, Two features where having some values repeted many time in the data so filled the NaN values of this features with mean of top 10 most occuring values. Filled the remaining features missing value by mean of entire feature. As 'diameter' was the target variable so its missing values was needed to be droped. Then converted the 'diameter' to float type variable.
  
  
  <div>
    <br>
    4. Handeling Outliers
  </div>
  Roughly estimeted the number of outliers using box plot visualization. Then found the actual number of outliers greater then 4th Standard Deviation using Z-Score Method. Finally created a Upper Limit and Lower Limit of outliers using InterQunatile Range and used Capping method to treat this outliers(i.e Replacing the values greater then Upper limit with Upper limit and replacing the values lower then lower limit by lower limit.)
  
  <br>
  <br>
  Saved the Clean Dataset with name 'Clean_Dataset.csv'
</div>

<div align="center">

### ✅ Data Visualization 💯
  
</div>
<div align="center">
  
#### File Name -> Data_Visualization.ipynb

</div>
<div align="center">
  1. Imported 'Clean_Dataset.csv' dataset for visualization
  <br>
  2. Designed a heatmap of correlation with annotation
  <br>
  3. Designed a scatter plot for feature 'a' VS 'n'
  <br>
  4. Designed a scatter plot for feature 'n' VS 'per_y'
  <br>
  5. Designed a count plot for categorical feature 'class'
  <br>
  6. Designed a categorical scatter plot for features 'class' VS 'data_arc'
  <br>
  7. Designed a categorical scatter plot for features 'ma' VS 'class'
  <br>
  8. Designed a multi-categorical scatter plot for feature 'class' VS 'per' with hue as 'pha'
  <br>
  9. Designed a box plot for feature 'class' VS 'Diameter'
  <br>
  10. Designed a point plot for feature 'pha' VS 'Diameter'
  <br>
  11. Designed a point plot for feature 'condition_code' VS 'Diameter'
  <br>
  12. Designed a point plot for feature 'condition_code' VS 'a'
  <br>
  13. Designed a kde plot of 'Diameter' VS 'Density'
  <br>
  14. Designed a kde plot of 'Diameter' VS 'Density' with hue as 'class'
  <br>
  15. Designed a Distribution Histogram for feature 'a'
  <br>
  16. Designed a Distribution Histogram for feature 'i'
</div>

<div align="center">

### ✅ Model Formation and Evaluation 💯
  
</div>
<div align="center">
  
#### File Name -> Model_Train_Test.ipynb

</div>
<div align="center">
  1. Imported 'Clean_Dataset.csv' dataset for model formation.
  <br>
  2. Converted Categorical Data into numeric using Dummy Variable Trap (Droping one dummy variable column as it can be predicted by other).
  <br>
  3. Splited the Data into Training and Testing Data ( 80 % of Data is used for Training and Testing is performed on 20% of data).
  <br>
  4. Scaled the Data between 0 and 1 using Standard Scaler.
  <br>
  5. Designed a evaluation function which will return Mean Absolute Error, Mean Squared Error, Root Mean Squared Error, R-Squared Value of the Model.
  <br>
  6. Algorithms and their R-Squared Values :
  <div align="center">
       A) Random Forest :-> 0.8104
      <br>
       B) K Nearest Neighbour :-> 0.7538
      <br>
      C) Linear Regression :-> 0.6358
      <br>
      D) Decision Tree :-> 0.6750
      <br>
      E) XG Boost :-> 0.8101
      <br>
      F) Optimized XG Boost :-> 0.8140
      <br>
      G) Artificial Neural Network :-> 0.7790   
  </div>
  7. Designed a 'Algorithm VS 'R-Squared' barplot for visualization and comaring the performance of Algorithms
  <br>
  <br>
  <b> 🌟 Conclusion :  Best performing model is XG Boost with HyperParameter Optimization. 🌟</b>
</div>

<div align="center">

### ✅ Model Updation 1 💯
  
</div>
<div align="center">
  
#### File Name -> Model_Train_Test_Update1.ipynb

</div>

<div align="center">
  To increase the accuracy of Model I have performed additional updates as followes :
  <br>
  <br>
  1. Checked for multi-collinearity in the data using variance inflation factor and eliminated such features having very high value.
  <br>
  2. Used 85% of data for training and performed testing on 15% of data.
  <br>
  3. Applied an additional Algorithm along with previous ones and Imporved R-Squared values where as follows : 
  <br>
   <div align="center">
       A) Random Forest :-> 0.8128
      <br>
       B) K Nearest Neighbour :-> 0.7530
      <br>
      C) Linear Regression :-> 0.6347
      <br>
      D) Decision Tree :-> 0.6771
      <br>
      E) XG Boost :-> 0.8125
      <br>
      F) Optimized XG Boost :-> 0.8170
      <br>
      G) Artificial Neural Network :-> 0.7830   
      <br>
      H) CatBoost Regressor :-> 0.8183
  </div>
  <br>
  <b> 🌟 Conclusion After Update 1: Best Performing Model is CatBoost Regressor. 🌟 </b> 
</div>
<div align="center">

### ✅ Model Updation 2 💯
  
</div>
<div align="center">
  
#### File Name -> Model_Train_Test_Update2.ipynb

</div>
    
 <div align="center">
  To further increase the accuracy of Model I have performed additional updates as followes :
  <br>
  <br>
  1. Used MinMax Scaler instead of Standard Scaler.
  <br>
  2. Increased the number of iterations on CatBoost Regressor.
  <br>
  Imporved R-Squared values where as follows : 
  <br>
   <div align="center">
       A) Random Forest :-> 0.8126
      <br>
       B) K Nearest Neighbour :-> 0.7364
      <br>
      C) Linear Regression :-> 0.6349
      <br>
      D) Decision Tree :-> 0.6808
      <br>
      E) XG Boost :-> 0.8124
      <br>
      F) Optimized XG Boost :-> 0.8171
      <br>
      G) Artificial Neural Network :-> 0.7709   
      <br>
      H) CatBoost Regressor :-> 0.8216
  </div>
  <br>
  <b> 🌟 Conclusion After Update 2: Best Performing Model is CatBoost Regressor. 🌟 </b> 
</div>

 <div align="center">

### ✅ Model Updation 3 💯
  
</div>
<div align="center">
  
#### File Name -> Model_Train_Test_Update3.ipynb

</div>
 
 <div align="center">
  To further increase the accuracy of Model I have performed additional updates as followes :
  <br>
  <br>
  1. Droped the feature only when its NaN values are greater then 90%
  <br>
  2. Instead of droping the NaN values of target variable (i.e 'diameter') filled those values with mean of the data.
  <br>
  3. Droped the rows which where the outliers of target variable (i.e 'diameter')
  <br>
  4. Used LabelEncoding for converting categorical variables('neo', 'pha') into Numeric.
  <br>
  5. Used 80% data for Training and performed Testing on 20% data.
  <br>
  Imporved R-Squared values where as follows : 
  <br>
   <div align="center">
       A) Random Forest :-> 0.9548
      <br>
       B) K Nearest Neighbour :-> 0.7567
      <br>
       C) Decision Tree :-> 0.9123
      <br>
       D) XG Boost :-> 0.9558
      <br>
       E) Artificial Neural Network :-> 0.8686   
      <br>
       F) CatBoost Regressor :-> 0.9572
  </div>
  <br>
  <b> 🌟 Conclusion After Update 3: Best Performing Model is CatBoost Regressor. 🌟 </b> 
</div>
</div>
