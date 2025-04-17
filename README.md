# 🌟 Facial Mood Detection for Song Recommendation 🎶

Welcome to the **Facial Mood Detection for Song Recommendation** project! This system uses facial landmarks detected via **Mediapipe** to analyze your facial mood and recommend songs that match your current emotion. 🎵😊

## 🚀 Project Overview

This system consists of four primary Python scripts:
1. **`data_collection.py`**: Captures facial landmarks and stores them for training the model. 📷🧑‍💻
2. **`data_training.py`**: Trains the model on the collected data to classify moods. 🧠💻
3. **`inference.py`**: Detects moods in real-time and recommends a song based on the mood. 🎤💃
4. **`tempcoderunnerfile.py`**: An alternate version of the data collection script for temporary testing. 🧪

## 🛠️ Installation

1. Install the required dependencies:
    ```bash
    pip install mediapipe opencv-python tensorflow keras numpy
    ```

2. Ensure you have a webcam connected to your computer for real-time facial mood detection. 🎥

## 📄 Script Descriptions

### 1. `data_collection.py` 📝

This script collects facial landmarks using **Mediapipe** and saves them as `.npy` files for later training.

- **How to Use**: Run the script, provide a name for the data file, and make various facial expressions (e.g., happy, sad, angry). The data will be captured and saved.
- **Features**:
  - Captures facial landmarks such as eyes, nose, and mouth.
  - Saves the landmarks relative to the face’s center.
  - The script captures 99 samples per mood by default.

### 2. `data_training.py` 🤖

This script trains a neural network model using the collected facial mood data.

- **How to Use**: After collecting the data, run this script to train a model that classifies different moods based on the facial expressions.
- **Features**:
  - Loads data from `.npy` files.
  - One-hot encodes the mood labels (e.g., "happy", "sad").
  - The model uses Keras and has layers with ReLU activation for classification.

### 3. `inference.py` 👁️

This script uses the trained model to detect facial moods in real-time and recommend songs based on the detected mood.

- **How to Use**: After training the model, run this script to detect facial moods in real-time and get song recommendations based on the detected mood.
- **Features**:
  - Detects facial landmarks and predicts the mood.
  - Recommends songs based on the detected mood (e.g., happy = upbeat song, sad = calming song).

### 4. `tempcoderunnerfile.py` 🧪

An alternate version of `data_collection.py` for temporary testing. Functions the same as `data_collection.py`.

## 🧠 Model Architecture

The deep learning model in `data_training.py` is a simple neural network designed with Keras:
- **Input Layer**: Takes input as the facial landmark features from the webcam feed.
- **Hidden Layers**: Two dense layers with ReLU activation functions.
- **Output Layer**: Softmax activation to classify moods (happy, sad, angry, etc.).

The model is compiled using `rmsprop` optimizer and `categorical_crossentropy` loss.

## 🎶 Song Recommendation System

- Once the mood is detected (happy, sad, angry, etc.), the system recommends a song based on predefined mood-to-song associations.
- **Example Moods and Song Recommendations**:
  - **Happy** 😊: Upbeat pop, energetic tracks 🎧🎶
  - **Sad** 😢: Calming, mellow tunes 🎼
  - **Angry** 😡: Intense rock, high-energy music 🎸

Songs can be customized based on user preferences or predefined playlists.

## 📂 File Outputs

- **`model.h5`**: The trained deep learning model.
- **`labels.npy`**: The mood labels associated with each facial expression (e.g., happy, sad, angry).
- **`.npy` files**: Contain the raw landmark data for each mood.

## 🔥 Real-time Inference

After training the model, use `inference.py` for real-time mood detection. The system will capture facial landmarks and predict the mood based on them. It will then recommend a song accordingly! 🎤🎵

## 📑 Usage Guide

### 1. Data Collection 📸
- Run `data_collection.py`.
- Provide a name for the dataset.
- Make facial expressions (e.g., happy, sad, angry).
- After 99 samples, the data will be saved as `.npy` files.

### 2. Train the Model 🧑‍🏫
- Run `data_training.py`.
- The script will load the `.npy` data, train the neural network model, and save the trained model as `model.h5`.

### 3. Mood Detection and Song Recommendation 🎶
- Run `inference.py`.
- The webcam feed will be displayed, showing the real-time detection of facial moods.
- Based on the mood, the system will recommend a song. 🎧🎤

## 📦 Dependencies

- **mediapipe**: For detecting facial landmarks.
- **opencv-python**: For capturing and displaying video frames.
- **tensorflow** and **keras**: For building and training the deep learning model.
- **numpy**: For handling data manipulation and processing.

## 🎉 Conclusion

This project demonstrates how to combine **Mediapipe**, **facial recognition**, and **deep learning** to classify facial moods and recommend music accordingly. You can extend this system by adding more moods, improving the model accuracy, or integrating it with a streaming service for automatic song recommendations! 🎶

