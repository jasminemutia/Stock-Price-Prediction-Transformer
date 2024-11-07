# Stock Price Prediction using Transformer
This project uses a Transformer model to predict stock prices for IBM and Facebook by analyzing historical data. 
The focus is on building a model that captures complex time-series patterns for improved accuracy. 
The process involves data preprocessing, model building, and fine-tuning to evaluate predictive performance.

## Access the Project
[IBM and Facebook Stock Price Prediction using Transformer](https://colab.research.google.com/drive/1x8V6wXdcYQIPFjT7ynzvyEvof_nZD6Cs?usp=sharing)

## Data Preprocessing
1. Import Libraries and Datasets: Starts with loading necessary libraries and datasets for IBM and Facebook stock prices.
2. Data Cleansing: Includes checking for missing and duplicate values, converting date columns, and selecting relevant columns (like Date and Close Price).
3. Data Splitting: Creates training, validation, and testing sets for both IBM and Facebook datasets.

## Baseline Transformer Model
- Architecture Overview: Implements a baseline Transformer model with an embedding layer, attention layer, and a feedforward layer, followed by normalization steps.
- Custom Model Definition: Utilizes transformerModel and modifymodel functions to define the baseline and modified Transformer architectures.
- Hyperparameter Tuning: Modifications include reducing the number of heads, decreasing transformer blocks, and adding dropout layers to combat overfitting. Training is conducted for 15 epochs with a batch size of 64.

## Model Training and Loss Analysis
- Training Output: The model’s performance is tracked via Mean Absolute Error (MAE) and Mean Squared Error (MSE) on both training and validation datasets. Loss values generally decrease across epochs, indicating convergence.

## Model Evaluation
1. Baseline Evaluation Metrics: Evaluation on the IBM dataset using RMSE, MAE, and MAPE to assess predictive accuracy.
2. Prediction and Plotting: The notebook includes a function to visualize real vs. predicted stock prices, showing that the model tracks trends effectively, with minimal deviation.
3. Comparison of Baseline and Modified Models: The modified model shows slight improvements in RMSE, MAE, and MAPE, suggesting that adjustments like dropout regularization help reduce overfitting.
