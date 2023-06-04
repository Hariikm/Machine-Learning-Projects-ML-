# Property-Price-Prediction
## Employing XGBoost regression and advanced data science techniques, I successfully improved  the R2score of the base model from negatives to an impressive 75%

![image](https://github.com/Hariikm/Property-Price-Prediction/assets/127305068/8a7757db-efc8-4e6d-ae97-694baf579b88)
<br><br>

🔷 Problem Statement: We have a dataset containing information about different properties in banglore loacation. The dataset includes the following columns:

🔸area_type: Describes the type of area the property is located in (e.g., Super built-up Area, Built-up Area, Plot Area, Carpet Area).<br>
🔸availability: Indicates the date of property availability<br>
🔸location: Specifies the location of the property.<br>
🔸size: Represents the size or number of rooms in the property (e.g., 2 BHK, 3 BHK).<br>
🔸society: Indicates the name of the society or housing complex the property belongs to.<br>
🔸total_sqft: Specifies the total square footage of the property.<br>
🔸bath: Represents the number of bathrooms in the property.<br>
🔸balcony: Indicates the number of balconies available in the property.<br>
🔸price: Represents the price of the property.<br>

<br><br>

🔷 Objective : Our objective is to develop a predictive model that can accurately estimate the price of a property based on its features.

To address this , we will:

🔸Explore and analyze the dataset, understanding the distribution and characteristics of the data.<br>
🔸Preprocess the data, handling missing values, outliers, and ensuring data quality.<br>
🔸Perform feature engineering, transforming and selecting relevant features for the model.<br>
🔸Choose an appropriate machine learning algorithm for regression.<br>
🔸Train the model using the dataset, optimizing its parameters if necessary.<br>
🔸Evaluate the model's performance using suitable metrics such as mean absolute error or root mean squared error.<br>
🔸Utilize the trained model to predict the price of new properties based on their features.<br>
🔸The success of our project will be determined by the model's ability to provide accurate price predictions for new properties.<br>

<br><br>

🔷 Raw Dataset Description

![image](https://github.com/Hariikm/Property-Price-Prediction/assets/127305068/b82909e7-5d37-48e6-8ed8-93ce7898512d)
<br><br>
🔷 Raw Dataset info<br><br>
![image](https://github.com/Hariikm/Property-Price-Prediction/assets/127305068/4ecfe90f-11e2-4a04-a73e-dc470264e465)
<br>
<br>

<br>

🔷 Basic Data Preprocessing

🔸Removed duplicated records and as well as null values from the data frame.<br>
🔸Converted the availability columns from a specific date to number of days left for availability.<br>
🔸Converted the size column from object datatype into BHK having only numeric values.<br>
🔸Deleted the society column as in further analysis it is observed as insignificant.<br>
🔸Cleaned the total_sqr column which was having ‘-’, ‘sq’ etc into only float datatypes.<br>
🔸Dropped the only 46 data which were null values left in total_sqft.<br>
🔸Filled the null values in Bath and Balcony using Iterative Imputer.<br>
🔸Aggregated a total of 1061 locations into the 'Others' category, which encompassed locations with a count of less than 11.<br>
🔸Used fuzzywuzzy algorithm to check the similarity between locations and grouped them further<br>
<br><br>
🔷 Basic EDA<br><br>
![image](https://github.com/Hariikm/Property-Price-Prediction/assets/127305068/10bff0b2-1ee1-4099-98e8-24a2251a0601)

<br><br>

🔷 Base Model<br><br>
![image](https://github.com/Hariikm/Property-Price-Prediction/assets/127305068/416f6d5f-e65e-4ed6-b136-2f5f86e00ded)<br>

<br><br>

🔷 Advanced Data Processing<br><br>

🔸Dropped data points having 0 square feet and also those having less than 250 sqfts per BHK.<br>
🔸Dropped data points having bathroom having more than 2 of BHK.<br>
🔸Dropped the outliers in price having values more or less than 1.5 times of standard deviation from the mean.<br>
🔸Dropped the data points with prices lower than the average price of properties with fewer bedrooms.<br>
🔸Dropped data points having BHK greater than 9 because the price of that doesn’t act as usual.<br>

<br><br>

🔷 Finding the Best Model<br><br>
![image](https://github.com/Hariikm/Property-Price-Prediction/assets/127305068/2db83189-4381-429d-83db-2d6d8f6e4e4f)<br><br>
🔸From this we identified that XGboost is the best algorithm to build the final model.

<br><br>

🔷 Feature Engineering<br><br>

![image](https://github.com/Hariikm/Property-Price-Prediction/assets/127305068/4f23b2c0-7cbd-4918-8488-e1bfd475fc48)<br><br>
🔸From this we identified that bath, balcony doesn’t got much significance so we drop it.

<br><br>

🔷 Final Model Building<br>
<br>
🔸We converted the locations and area _type into dummy variables through one-hot-encoding.<br>
🔸We have also did hyperparameter tuning using GridSearchCV<br>
🔸We then build the final model using XGBoost Regressor with the following scores : <br><br>
![image](https://github.com/Hariikm/Property-Price-Prediction/assets/127305068/f97bd87b-cc83-4a1c-87c6-aa7a5369f96f)<br>

<br><br>

🔷 Final Output<br><br>
![image](https://github.com/Hariikm/Property-Price-Prediction/assets/127305068/f6ad934a-9719-4a7e-ba89-7549a78fa2de)
