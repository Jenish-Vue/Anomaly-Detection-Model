# Anomaly Detection Model using LSTM Autoencoder

This project implements an Anomaly Detection Model based on LSTM Autoencoder to identify anomalies in time-series data, particularly for stock market prices (e.g., S&P 500 index). The LSTM Autoencoder architecture is used for unsupervised anomaly detection, which detects unusual patterns in a time series that do not conform to expected behavior.

## Project Overview

The goal of this project is to detect anomalies in time-series data using an LSTM Autoencoder. The project uses LSTM (Long Short-Term Memory) networks as part of an Autoencoder architecture, where the model is trained to learn a compact representation of the data and reconstruct it. By comparing the original and reconstructed data, anomalies can be detected based on reconstruction errors.

## Key Features:

  Detect anomalies in time series data.
  Use LSTM Autoencoders for anomaly detection.
  Implement data preprocessing and normalization.
  Calculate loss for anomaly detection.
  Visualize results and anomalies.

## Dataset

The project uses historical stock market data. The dataset is fetched using the Yahoo Finance API via the yfinance library. In this project stock data for the S&P 500 index from 1980 to 2023 is uploaded using yahoo finance library


## Model Architecture

The core of this project is an LSTM Autoencoder used for anomaly detection. The architecture consists of:

    Encoder: An LSTM network that learns a compressed representation of the input time-series data.
    Decoder: A reverse LSTM network that attempts to reconstruct the input from the compressed representation.
    Anomaly Detection: The model calculates the reconstruction loss between the input and the output. Data points with high reconstruction loss are considered anomalies.

The model's architecture is as follows:

    LSTM Encoder layers with varying sizes (e.g., 64, 32, 16).
    Repeat Vector to bridge the encoder and decoder.
    LSTM Decoder layers with reversed sizes.
    Final output using TimeDistributed(Dense).

## Steps
### 1. Data Collection:
        Use the yfinance library to download stock data (or use any other time-series data).
        Preprocess and normalize the data using MinMaxScaler.

### 2. Create the LSTM Autoencoder:
        Define the LSTM Autoencoder architecture using Keras or TensorFlow.
        Train the model on the normalized data.

### 3. Calculate Reconstruction Loss:
        After training, calculate the reconstruction error on the test set.
        Use a threshold to identify anomalies based on the reconstruction loss.

### 4. Detect Anomalies:
        Mark data points with high reconstruction error as anomalies.
        Optionally, visualize the anomalies using matplotlib and seaborn.

### 5.Evaluate the Results:
        Analyze the detected anomalies and their relevance to the dataset.

### Results

     The model learns to reconstruct the time-series data and detects anomalies by evaluating the reconstruction error. A threshold for the error is used to classify data points as normal or anomalous.
     The results are visualized in the time series with the anomalies highlighted.

