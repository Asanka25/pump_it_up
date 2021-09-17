### Pump it up solution (170482R)

1. Exploratory data analysis

  Insights about data types, distributions, and missing values. Have only object and int type data columns. Train data isn&#39;t a balanced dataset. Missing values can be      found in scheme\_name, status\_group, scheme\_management, installer , funder, public\_meeting, permit , subvillage columns

2. Drop columns using insights of EDA

By EDA realize that only amount\_tsh, funder, gps\_height, installer, longitude, latitude, basin, region, district\_code, lga, ward, population, public\_meeting, permit, construction\_year, extraction\_type\_group, management, payment, water\_quality,quantity, source, waterpoint\_type, status\_group are useful. Dropped remaining columns

3. Filling missing values

For numerical values used mean of the column to fill missing values

For funder and installer columns used &#39;Unknown&#39; to fill missing values and replaces &#39;0&#39; value also with &#39;Unknown&#39;. Could find that there are spelling mistakes in the funder and installer columns, corrected those mistakes aswell.

4. Selecting best features

- Used sequence feature selection (Used Random forest, XGboost and Catboost as classifiers)
- Used correlation with target variable
- First train Random Forest and used feature importance property to select features

5. Generating features

- Used PCA and created and one feature from selected columns and add it to the dataset
- Tried creating new features using grouping with other feature
- Used Clustering to create feature using features like longitude, latitude, extraction\_type\_group and region

6. Outlier detection using boxplots

Removed those identified outliers and check whether any improvement can be achieved

7. Evaluating models using 5 fold cross validation

- Random forest
- Catboost
- XGBoost
- KNN
