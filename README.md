# Stock Price Prediction using Transformer
This project uses a Transformer model to predict stock prices for IBM and Facebook by analyzing historical data. 
The focus is on building a model that captures complex time-series patterns for improved accuracy. 
The process involves data preprocessing, model building, and fine-tuning to evaluate predictive performance.

## Access the Project
[IBM and Facebook Stock Price Prediction using Transformer](https://colab.research.google.com/drive/1x8V6wXdcYQIPFjT7ynzvyEvof_nZD6Cs?usp=sharing)

## IBM and Facebook Stock Data
- IBM Dataset: Contains approximately 14,663 rows of daily stock data.
- Facebook Dataset: Similar in structure to IBM, with around 1,980 rows of daily stock data as well.
- Columns:
  - Date: Indicates the trading date for each entry.
  - Open: Opening price of the stock on a given day.
  - High: The highest trading price for the stock on that day.
  - Low: The lowest trading price.
  - Close: The closing price, which is the main target for prediction.
  - Volume: Number of shares traded during that day.

## Data Preprocessing
1. Import Libraries and Datasets: Starts with loading necessary libraries and datasets for IBM and Facebook stock prices.
2. Data Cleansing: Includes checking for missing and duplicate values, converting date columns, and selecting relevant columns (like Date and Close Price).
3. Feature Selection: Only the Date and Close columns are used to keep the focus on closing price prediction, although other columns (e.g., Volume) could be used in future enhancements.
4. Data Splitting: Creates training, validation, and testing sets for both IBM and Facebook datasets.

## Baseline Transformer Model
- Embedding Layer: Converts the input price data into a higher-dimensional space suitable for the Transformer’s operations.
- Self-Attention Layer: Allows the model to consider relationships across the time sequence by focusing on relevant past data points.
  - Multi-Head Attention: Uses multiple attention heads, each capturing different time-dependent patterns (short- and long-term trends).
- Feedforward Layer: A dense layer that applies a transformation to the attention output, helping the model learn complex interactions in stock movements.
- Layer Normalization: Normalizes the data within layers, improving convergence during training.
- Output Layer: Predicts the closing price for the next time step based on learned patterns.

## Modified Transformer Model
Changes for Enhanced Performance:
- Reduced Number of Attention Heads: Simplifies the model by lowering the number of attention heads, reducing overfitting.
- Decreased Transformer Blocks: Reducing the number of stacked Transformer layers prevents excessive complexity and overfitting.
- Dropout Layers: Introduced between Transformer blocks to randomly omit neurons during training, improving generalization.
- Training Configuration: The modified model is trained for 15 epochs with a batch size of 64 to balance performance and training efficiency.

## Model Training and Loss Analysis
- Training Output: The model’s performance is tracked via Mean Absolute Error (MAE) and Mean Squared Error (MSE) on both training and validation datasets. Loss values generally decrease across epochs, indicating convergence.

## Model Evaluation
1. Baseline Evaluation Metrics: Evaluation on the IBM dataset using RMSE, MAE, and MAPE to assess predictive accuracy.
2. Prediction and Plotting: The notebook includes a function to visualize real vs. predicted stock prices, showing that the model tracks trends effectively, with minimal deviation.
3. Comparison of Baseline and Modified Models: The modified model shows slight improvements in RMSE, MAE, and MAPE, suggesting that adjustments like dropout regularization help reduce overfitting.
