# Tik Tok 

## Project Overview

This project involves the evaluation, comparison, and optimization of multiple regression models using a TikTok dataset. The primary goal is to predict the number of likes on a TikTok video based on various features of the dataset. Several models, including Linear Regression, Ridge Regression, Lasso Regression, Elastic Net, Bayesian Ridge, Decision Tree Regressor, SGD Regressor, K-Nearest Neighbors Regressor, and XGBoost Regressor, have been trained, evaluated, and compared.

## Dataset

The dataset contains various features related to TikTok videos, including:

- **video_duration_sec**: Duration of the video in seconds.
- **video_view_count**: Total number of views the video has received.
- **video_like_count**: Total number of likes the video has received (target variable).
- **video_share_count**: Total number of times the video has been shared.
- **video_download_count**: Total number of times the video has been downloaded.
- **video_comment_count**: Total number of comments on the video.
- **claim_status**: Indicates whether the video has been reported for containing a claim or opinion.
- **verified_status**: Indicates whether the video creator's account is verified.
- **author_ban_status**: Indicates if the video's author has been banned.

## Key Steps

### 1. Data Preprocessing
- Dropped irrelevant columns (`video_id`, `video_transcription_text`).
- Checked for and dropped any rows with missing values.
- One-hot encoded categorical variables.
- Scaled the numerical data using `StandardScaler`.

### 2. Correlation Analysis
- Created a correlation matrix to analyze the relationship between features and the target variable (`video_like_count`).
- Dropped features with low correlation with `video_like_count` to reduce dimensionality.

### 3. Model Training and Evaluation
- Trained multiple regression models, including:
  - Linear Regression
  - Ridge Regression
  - Lasso Regression
  - Elastic Net
  - Bayesian Ridge
  - Decision Tree Regressor
  - SGD Regressor
  - K-Nearest Neighbors Regressor
  - XGBoost Regressor
- Evaluated each model using Mean Absolute Error (MAE), Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and R² Score.
- Sorted the models by R² Score to identify the best-performing model.

### 4. Model Comparison
- Compared the performance of all models by organizing the evaluation metrics into a DataFrame.
- Performed a hard voting ensemble method on the top-performing models (KNN, XGBoost, SGD, Linear, Lasso, Ridge).

## Results

The evaluation metrics for all models were printed in descending order based on R² Score. The following models were found to perform best in predicting the number of likes on a TikTok video:

1. K-Nearest Neighbors Regressor
2. XGBoost Regressor
3. SGD Regressor
4. Linear Regression
5. Lasso Regression
6. Ridge Regression

## Future Work

To improve the model's accuracy:

- Experiment with hyperparameter tuning for each model.
- Explore other ensemble methods such as stacking or bagging.
- Test additional feature engineering techniques.

## Code Structure

- **Data Preprocessing and Cleaning**: All data preprocessing steps, including handling missing values, one-hot encoding, and scaling.
- **Model Training**: Code to train and evaluate each model.
- **Model Comparison**: Code to create and print a DataFrame of model evaluation metrics.
- **Ensemble Methods**: Implementation of a hard voting ensemble for the top-performing models.

## Dependencies

- Python 3.x
- pandas
- scikit-learn
- XGBoost
- numpy
- seaborn
- matplotlib
