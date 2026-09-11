# Assignment 4 – LSTM-Based Stock Price Forecasting

## Aim

To develop an LSTM-based model for time-series forecasting using
historical stock-price data.

## Objective

To build an LSTM neural network that learns patterns from historical
AAPL stock prices and predicts future closing prices.

## Dataset

The dataset contains historical Apple (AAPL) stock-price information.

Columns include:

- Open
- High
- Low
- Close
- Adj Close
- Volume

The Closing Price is used as the target variable.

## Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- TensorFlow
- Keras

## Methodology

1. Load the AAPL stock-price dataset.
2. Explore the dataset.
3. Prepare the date information.
4. Visualize historical closing prices.
5. Select the closing price.
6. Normalize the data using MinMaxScaler.
7. Create sequences using 60 previous trading days.
8. Split the data into training and testing sets.
9. Build an LSTM neural network.
10. Train the model.
11. Generate predictions.
12. Convert predictions back to the original scale.
13. Evaluate the model using MAE and RMSE.
14. Compare actual and predicted prices.
15. Predict the next closing price.

## Model Architecture

- LSTM Layer – 50 units
- Dropout – 20%
- LSTM Layer – 50 units
- Dropout – 20%
- Dense Layer – 25 units
- Output Layer – 1 unit

## Evaluation Metrics

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)

## Conclusion
In this assignment, an LSTM-based time-series forecasting model was
developed using historical Apple (AAPL) stock-price data.

The closing price was selected as the target variable. The data was
preprocessed and normalized using Min-Max scaling. Sequential samples
were then created using the previous 60 trading days to predict the
next day's closing price.

An LSTM neural network containing two LSTM layers was trained using
the historical stock-price sequences. The model was evaluated using
Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE).

The Actual vs Predicted graph was used to visually compare the model's
predictions with the actual stock prices.

The experiment demonstrates that LSTM networks can learn sequential
patterns in time-series data and can be applied to stock-price
forecasting.