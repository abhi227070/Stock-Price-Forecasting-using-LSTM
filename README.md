

```markdown
# Stock Price Prediction using LSTM

This project focuses on predicting stock prices using Long Short-Term Memory (LSTM) neural networks. It involves the following key steps: data collection, data preprocessing, model building, training, and prediction.

## Data Collection

The data is collected from Tiingo using the pandas datareader library. An API key is used to access the data.

```python
import pandas_datareader as pdr

df = pdr.get_data_tiingo('GOOGL', api_key='1fb09ab6945c3ec3a50df8c02d5b65ecf8ce5975')
```

## Data Preprocessing

The collected data is converted into a CSV file for further analysis.

```python
df.to_csv('COUR.csv')
```

Pandas is used to read the CSV data, and the 'close' column is extracted for analysis.

## Data Analysis and Visualization

The stock price data is analyzed and visualized using matplotlib.

```python
import matplotlib.pyplot as plt
plt.figure(figsize=(12, 8))
plt.plot(new_df)
```

## Data Scaling

The stock price data is scaled using MinMaxScaler from scikit-learn to bring it within a range of 0 to 1.

## Creating Training and Testing Data

The data is split into training and testing sets to train and evaluate the model's performance.

## Model Building

A sequential LSTM model is created using TensorFlow and Keras.

```python
model = Sequential()

model.add(LSTM(50, return_sequences=True, input_shape=(100, 1)))
model.add(LSTM(50, return_sequences=True))
model.add(LSTM(50))
model.add(Dense(1))

model.compile(loss='mse', optimizer='adam')
```

## Model Training

The LSTM model is trained using the training data.

```python
model.fit(x_train, y_train, validation_data=(x_test, y_test), epochs=10)
```

## Model Prediction

The trained model is used to make predictions on both the training and testing data.

## Model Evaluation

The mean squared error (MSE) is calculated to evaluate the model's performance.

## Future Stock Price Prediction

The model is used to predict the stock price for the next 30 days. This involves iterative predictions based on the model's previous outputs.

## Visualization of Predicted Prices

The predicted stock prices are visualized, along with the actual prices, to assess the model's accuracy.

## Saving the Model

The trained LSTM model is saved for future use.

```python
model.save('model.h5')
```
