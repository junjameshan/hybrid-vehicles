# Hybrid Vehicle Pricing 

### Data Analysis and Regression on Hybrid Vehicle Pricing over time 

![image](https://user-images.githubusercontent.com/123096758/230461837-a66221cf-a4ec-435a-b8c6-fbfe98cece2b.png)

## Background 

Hybrid vehicles have been around for many years over time but have recently started to see a surge in its popularity of sales and ownership with customers across the world. In order to best understand the correlation between each of the attributes of hybrid vehicles, we want to explore the independent variables that correlate to the total price of a hybrid vehicle. 

## Attributes within the Hybrid Vehicles Dataset 

[Link to Hybrid Vehicles Dataset](https://github.com/junjameshan/hybrid-vehicles/blob/main/data/hybrid_vehicle_price_data.csv)

* carid: Unique identifier for each vehicle 
* vehicle: Name of vehicle 
* year: Year of release for vehicle
* msrp: Manufacturer's Suggested Retail Price 
* accelrate: Time it takes the vehicle to accelerate from 0-60 mph (in seconds) 
* mpg: Miles Per Gallon
* mpgmpge: Miles Per Gallon Equivalent 
* carclass: Class type of vehicle 
* carclass_id: ID of class type of vehicle 

## Data Exploration 

In order to best understand how each of the attributes correlate to the price of a hybrid vehicle (msrp), I wanted to conduct a exploratory analysis on the dataset to visualize my initial assumptions on which attribute will most likely contribute to a price of a vehicle. 

The first visualization I created was a heat map to see the strength of correlation between each of the attributes. Based on the visualization, I have interested that there is a strong positive correlation between msrp and accelrate while there is a strong negative correlation between msrp and mpg. 

![image](https://user-images.githubusercontent.com/123096758/230466277-93f78f0c-275f-40ba-adc3-4ac31d95b2dc.png)

In order to visualize each of the variables, I created a visualization of a linear model plot to show the relationship between each attributes.


#### msrp vs. accelrate 

![image](https://user-images.githubusercontent.com/123096758/230466721-910039ca-5321-492b-b29d-88715666604e.png)

#### msrp vs. mpg

![image](https://user-images.githubusercontent.com/123096758/230466819-22d71b01-3b9d-44a7-bb65-e2f0528152c2.png)

From these results, we can make infer two hypotheses:

* As the value of accelrate increases for a vehicle, the msrp of a vehicle will also increase as well. 
* As the value of mpg increases for a vehicle, the price of a vehicle will decrease. 

## Train-Test Split for Linear Regression 

In order to develop the Linear Regression model based on the variavbles that we hypothesize will relate to the msrp of a vehicle, we had to train the model by using a model selection to split the data into training and testing sets. 

By looking through code lines 10 - 13, you can see the process in how this Train-Test Split process was done for developing the regression model. 

[Link to Jupyter Notebook](https://github.com/junjameshan/hybrid-vehicles/blob/main/Hybrid_Vehicles_Pricing.ipynb)

The Train-Test Split procedure is performed in order to compare the performance of machine learning algorithms for the predictive modeling problem. 


## Linear Regression Model Results 

Based on the results from the Linear Regression Model, I first sought to understand the coefficients of the model and how each attribute contributed to the msrp of a vehicle. 

| Attributes      | Coefficient   | 
| :-------------: |:-------------:| 
| accelrate       | 3934.96       | 
| mpg             | -613.24       |  

The results of the coefficients are interpreted as follows:

* A 1 unit increase in accelrate is associated with an increase of approximately 3,934.96 total dollars of msrp.
* A 1 unit increase in mpg is associated with a decrease of approximately 613.24 total dollars of msrp.

In order to evaluate the prediction of the test data and its performance to check to see if there is a linear relationship, a scatter plot was created in order to visualize the results. 

![image](https://user-images.githubusercontent.com/123096758/230472503-322ea20c-fdcc-4917-ac00-549edfc29b2f.png)


A histogram of the residuals was also visualized in order to check for normal distribution. 

![image](https://user-images.githubusercontent.com/123096758/230472618-8d2b711f-d094-4db9-96d9-7eb181b67db6.png)


Lastly, I calculated for the Mean Absolute Error (MAE), the Mean Squared Error (MSE), and the Root Mean Squared Error (RMSE) based on the test and prediction values. 

* **MAE**: 12250.45
* **MSE**: 254317985.97
* **RMSE**: 15947.35

## Conclusion 

Based on the results of my model development, I have concluded my findings to a few insights that I uncovered.

  1. The results and insights that I have interpreted based on my model is that there is a positive correlation
between the price of the vehicle (msrp) and accelrate while there is a negative correlation between the
msrp and the mpg of the vehicle. The insight that I drew from this analysis was that the overall
performance of a vehicle will result in a more expensive hybrid vehicle. This makes sense in that higher
performance vehicles with a greater horsepower in its engine will be making a trade-off in fuel
efficiency. Furthermore, higher performance vehicles require greater technology and engine
performance which will directly relate to a higher sticker price for the vehicles as well.

  2. The variables I chose to include in my model were accelrate and mpg as based on my analysis conducted
to determine a correlation for vehicle price. The visual graphs of the heat map, joint and scatter plots
were important in determining if there were any correlation between the variables and msrp and visually
represent what the relationship looked like.
The variables I chose to exclude were the car id, year of the vehicle, car class id and mpgmpge. I chose
to exclude these variables as there wasn’t a strong relationship between the variables excluded and the
price of the vehicle when analyzing the heat map correlation of each of the variables. The only variable
that had indicated a relationship was mpgmpge but opted to exclude this variable from my model results
as mpg and mpgmpge were similar in its values and the relationship can also be explained by mpg as
well. 

  3. The variables that had significant explanatory power on hybrid vehicle pricing were the variables of
accelrate and mpg. The variables that I found surprising to not have significant explanatory power were
the year and carclass of the vehicle. I found this to be surprising as I have hypothesized before
conducting my analysis that the year and make of the vehicle will be a contributing factor to the total
price of the vehicle. Newer vehicles are equipped with modern technology and automobile parts that can
drive up the sticker price of the vehicle while a car class of a SUV, Sedan, or even Truck are also
contributing factors to a total price of a vehicle as well. 







