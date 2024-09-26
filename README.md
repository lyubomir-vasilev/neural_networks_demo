# Stock Price Prediction using Long Short-Term Memory (LSTM)

## Overview
This project demonstrates how to predict stock prices using a **Long Short-Term Memory (LSTM)** model, a type of Recurrent Neural Network (RNN) well-suited for time-series data. We utilize historical stock data and macroeconomic indicators to predict future stock prices, specifically Apple's stock prices.

### What is LSTM?
LSTM (Long Short-Term Memory) is a special type of RNN that can retain long-term dependencies, making it ideal for working with sequential data like stock prices, which exhibit patterns over time. LSTM uses gates (input, forget, and output) to manage what information to keep or discard, which makes it effective for predicting future values based on past trends.

## Steps Followed
The project follows these main steps:
1. **Data Loading**: Stock data for Apple is fetched using Yahoo Finance and interest rates from FRED.
2. **Data Cleaning**: Handles missing data and ensures that numeric fields are properly formatted.
3. **Data Preparation**: Calculates moving averages and creates the dataset for training/testing.
4. **Data Scaling**: Uses `MinMaxScaler` to scale the data to a range of 0 to 1 for better performance.
5. **Model Building**: A Sequential LSTM model is created with two LSTM layers and one Dense layer.
6. **Model Training**: The model is trained using historical data with a batch size of 20 and 3 epochs.
7. **Model Testing**: The model is tested on unseen data.
8. **Evaluation**: Model performance is measured using Mean Squared Error (MSE) and Root Mean Squared Error (RMSE).
9. **Visualization**: The results (predicted vs actual prices) are plotted.

## Architecture

### First LSTM Layer:
- **LSTM(50, return_sequences=True)**: This layer has 50 neurons and returns all time steps, learning sequential dependencies from the input data.

### Second LSTM Layer:
- **LSTM(50, return_sequences=False)**: The second LSTM layer also has 50 neurons, but only returns the final output from the last time step.

### Dense Layer:
- **Dense(25)**: A fully connected layer with 25 neurons, used to extract additional features from the output of the LSTM layers.

### Final Dense Layer:
- **Dense(1)**: The final layer with a single neuron outputs the predicted stock price for the next day.

## Requirements
To run this project, you need the following libraries:

- pandas
- pandas-datareader
- numpy
- yfinance
- matplotlib
- scikit-learn
- keras
- tensorflow
- mplfinance

You can install these dependencies using the following command:

```bash
pip install -r requirements.txt
