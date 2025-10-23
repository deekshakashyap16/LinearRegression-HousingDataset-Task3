Task 3: Linear Regression Model (Housing Dataset)

This repository contains my solution for Task 3, focusing on building a linear regression model to predict house prices based on various features from the Housing dataset.

What did I do?
The goal was to build and evaluate a linear regression model that predicts housing prices using multiple features like area, bedrooms, bathrooms, and various amenities.

Data Preprocessing
I started by loading the Housing.csv dataset and checking for missing values using .isna().sum() - the dataset had no missing values, which was great for model building.

Feature Engineering:

Label Encoding: Applied to binary categorical features (mainroad, guestroom, basement, hotwaterheating, airconditioning, prefarea) converting 'yes'/'no' to 1/0.
One-Hot Encoding: Applied to the furnishingstatus column (furnished, semi-furnished, unfurnished) using drop='first' to avoid multicollinearity, creating two new binary columns.
Standardization: Applied StandardScaler to numerical features (price, area, bedrooms, bathrooms, stories, parking) to normalize their ranges while keeping binary features unchanged.

Model Building

I split the data into training (80%) and testing (20%) sets using train_test_split with random_state=42 for reproducibility.

Model Performance
The model achieved the following metrics:

Mean Absolute Error (MAE): 0.519 - On average, predictions deviate by about 0.52 units from actual values
Mean Squared Error (MSE): 0.502 - Indicates the variance of prediction errors
R^2 Score: 0.653 - The model explains approximately 65.3% of the variance in house prices

The R^2 Score shows that linear regression is unable to capture the data well, and a curved fit or a non linear model will be a more optimal approach. 

The scatter plot of actual vs predicted values showed a reasonably good fit with points clustering around the diagonal red line, though with some spread indicating room for improvement.

Interpreting the Regression Coefficients
Strongest Positive Predictors:

Airconditioning (0.42): Houses with AC command significantly higher prices
Prefarea (0.34): Being in a preferred area adds substantial value
Bathrooms (0.29): Each additional bathroom increases price notably
Area (0.27): Larger houses naturally cost more

Moderate Positive Predictors:

Basement (0.21): Having a basement adds decent value
Mainroad (0.20): Properties on main roads are valued higher
Stories (0.19): Multi-story houses command better prices

Weaker Predictors:

Guestroom (0.12) and Parking (0.10): Have minimal impact
Bedrooms (0.03): Surprisingly low coefficient, suggesting quality over quantity

Negative Predictors:

Unfurnished (-0.22): Significantly reduces price compared to furnished
Semi-furnished (-0.07): Slight decrease compared to fully furnished

Tools Used

Python,Pandas,NumPy,Scikit-learn,Matplotlib