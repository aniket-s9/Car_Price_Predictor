# Car_Price_Predictor
A machine learning project that predicts car prices using Multiple Linear Regression based on features like brand, year, fuel type, and mileage. It includes data preprocessing, model training, and evaluation to provide accurate price estimates.

## Overview
This project develops a linear regression model to predict car prices based on various features such as `Brand`, `Model_Year`, `Engine_Size`, `Fuel_Type`, `Transmission`, `Mileage`, `Doors`, `Owner_Count`, and `Horsepower`. The model is built using a custom implementation of gradient descent.

## Dataset
The dataset used for this project is `car_price_dataset.csv`, which contains information on various cars and their corresponding prices.

### Data Fields:
*   `Car_ID`: Unique identifier for each car.
*   `Brand`: Car manufacturer.
*   `Model_Year`: Year the car was manufactured.
*   `Engine_Size`: Engine capacity in liters.
*   `Fuel_Type`: Type of fuel used (e.g., Petrol, Diesel, Electric, Hybrid).
*   `Transmission`: Type of transmission (Manual, Automatic).
*   `Mileage`: Total distance traveled by the car.
*   `Doors`: Number of doors on the car.
*   `Owner_Count`: Number of previous owners.
*   `Horsepower`: Engine horsepower.
*   `Price`: Selling price of the car (target variable).

## Methodology

### 1. Data Loading and Preprocessing
*   The `car_price_dataset.csv` file was loaded into a pandas DataFrame.
*   Numerical features (`Model_Year`, `Engine_Size`, `Mileage`, `Doors`, `Owner_Count`, `Horsepower`) were selected as input features (`x`).
*   The `Price` column was selected as the target variable (`y`).
*   Numerical features were standardized (mean-centered and scaled to unit variance) to ensure proper functioning of the gradient descent algorithm.

### 2. Model Training (Linear Regression with Gradient Descent)
*   A custom linear regression model was implemented using batch gradient descent.
*   The model initializes weights (`w`) to zeros and bias (`b`) to zero.
*   The learning rate (`lr`) was set to `0.01` and the model was trained for `400` epochs.
*   During training, Mean Squared Error (MSE) was used as the loss function, and Root Mean Squared Error (RMSE) was tracked to monitor performance.

### 3. Model Evaluation
*   The data was split into training (80%) and testing (20%) sets to evaluate the model's generalization capabilities.
*   The model was trained on the training data and evaluated on the unseen test data.
*   The following metrics were calculated for the test set:
    *   **R-squared:** Measures the proportion of variance in the dependent variable that can be predicted from the independent variables. (Result: **0.9666**)
    *   **Mean Absolute Error (MAE):** The average of the absolute differences between predictions and actual observations. (Result: **$1441.20**)
    *   **Mean Squared Error (MSE):** The average of the squared differences between predictions and actual observations. (Result: **$2,754,452.97**)
    *   **Root Mean Squared Error (RMSE):** The square root of the average of the squared differences between predictions and actual observations. (Result: **$1659.65**)

### 4. Visualization
*   Plots of 'Epochs vs. Losses' and 'Epochs vs. RMSE' were generated to visualize the training progress and convergence.
*   A scatter plot of 'Actual vs. Predicted Car Prices' on the test set was created, including a diagonal line for perfect predictions, to visually assess the model's accuracy.

## Key Results
*   The model achieved an **R-squared score of 0.9666** on the test set, indicating that approximately 96.66% of the variance in car prices can be explained by the input features.
*   The RMSE on the test set was approximately **$1659.65**, suggesting that, on average, the model's predictions were off by about $1659.65.
*   The visualizations confirmed that the model converged effectively during training and its predictions closely align with the actual car prices.

## How to Run This Notebook
1.  **Download the Notebook:** Download the `car_price_prediction.ipynb` file from this repository.
2.  **Open in Google Colab:** Upload the `.ipynb` file to Google Colab, or open it directly in Colab.
3.  **Run All Cells:** Execute all the code cells sequentially. The notebook will:
    *   Load the dataset.
    *   Preprocess the data.
    *   Train the linear regression model.
    *   Evaluate the model's performance.
    *   Generate various plots for analysis.

## Files in This Repository
*   `car_price_prediction.ipynb`: The main Colab notebook containing all the code for data loading, preprocessing, model training, and evaluation.
*   `car_price_dataset.csv`: The dataset used in the project.
*   `README.md`: This file.

## Future Enhancements (Optional)
*   Explore more advanced regression models (e.g., RandomForest, XGBoost, Neural Networks).
*   Perform feature engineering (e.g., creating polynomial features, interaction terms).
*   Incorporate categorical features into the model using one-hot encoding or other techniques.
*   Hyperparameter tuning for optimal model performance.
*   Collect more data for improved accuracy.
