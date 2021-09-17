# pump_it_up

GitHub link - 

First, checked for the missing values in the given data and identified below features with missing values.

![Capture1](https://user-images.githubusercontent.com/47806722/133816352-3bdc015d-354c-41ba-b0ac-d823540f6808.PNG)

Then investigate statistic summary for each feature available. 

![Capture2](https://user-images.githubusercontent.com/47806722/133816400-c9df1cd8-8d7c-4d22-ac2e-9aa6857218a9.PNG)

Then plot a correlation heat map for numerical features for and no significant correlation between two features were found.

![Capture3](https://user-images.githubusercontent.com/47806722/133816447-c0bf202d-873e-40d8-9ec1-3a9f8f6236a3.PNG)

scheme_name feature has a lot of missing values. Those values were filled using the mode value for each region.

scheme_managemet feature only have 12 unique values and missing values were replaced using the mode value of scheme_managemet.

Public_meeting and permit features’ missing values replaced using the mode value of respective field.
Funder and installer features’ only top 10 values were used as separate categories. Other values consider as a separate category named “other”.

Dropped the subvillage feature.

Then plot a graph using longitude and latitude to observe the geographical distribution of data. And identified 1812 rows with 0,0 longitude and latitude which is clearly are some outlier due to false values. 

![download](https://user-images.githubusercontent.com/47806722/133816557-cc79cd64-678c-44b5-ab23-5f8112a4ba7a.png)

Data have addition field region code which gives some idea about geo graphical location. Calculated the median longitude and latitude for each region and use respective values for correct the outliers. After correcting the outliers longitude and latitude distribution was as follows. 

![download1](https://user-images.githubusercontent.com/47806722/133816612-8132e73a-0d33-47ca-ac1a-a0d4584b0de2.png)

Other dropped columns –
[date_recorded,gps_height,wpt_name,num_private,subvillage,lga,ward,recorded_by,extraction_type,management, management_group, payment , quality_group, quantity , source_type,  waterpoint_type_group, region] 

Use k-fold validation to evaluate the models.
Models tested-
1.	Random Forrest 
2.	XG boost classifier
3.	SVM

Random forest achieved the best cross validation scores and used it for final prediction after training on the whole dataset. This model was able to achieve 0.8124 score on data driven test dataset.

![Capture5](https://user-images.githubusercontent.com/47806722/133816740-01faf038-e47c-47c9-96a1-8ceb3ebfe0fb.PNG)


