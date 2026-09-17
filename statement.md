
# Project Statement

## Project Title

Apple Tree Disease Prediction Using Image Classification

## 1. Problem Statement

Apple trees can be affected by diseases such as rust, scab, and multiple diseases, which can reduce plant health and agricultural productivity. Manual disease identification can be time-consuming and requires specialized knowledge.

This project develops an image classification system using a Convolutional Neural Network (CNN) to classify apple leaf images into four categories: healthy, rust, scab, and multiple diseases. The system uses image preprocessing and deep learning techniques to learn visual patterns from labeled leaf images and predict the category of a new image.

## 2. Project Scope

The project focuses on developing a CNN-based image classification model for identifying apple tree leaf conditions.

The project includes:

- Loading training and testing labels from CSV files.
- Organizing image data into appropriate categories.
- Preprocessing and normalizing images.
- Creating training and validation data generators.
- Building and training a CNN model.
- Saving the trained model for future use.
- Predicting the category of an input apple leaf image.
- Visualizing training and validation accuracy and loss.

The project is developed for academic purposes and provides preliminary image-based classification rather than professional agricultural diagnosis.

## 3. Target Users

- Agriculture students and researchers.
- Students learning computer vision and deep learning.
- Farmers seeking preliminary information about apple leaf conditions.
- Developers exploring CNN-based image classification systems.

## 4. High-Level Features

### 4.1 Dataset Loading and Organization

The system loads image labels from `train.csv` and `test.csv`. The training labels include the image identifier and four classification categories: healthy, multiple diseases, rust, and scab.

### 4.2 Image Preprocessing

The project processes leaf images and prepares them for model training. Images are normalized using pixel rescaling, and data generators are used to supply images to the model.

### 4.3 CNN Model Development

A Convolutional Neural Network is developed using multiple convolutional layers, max-pooling layers, a flattening layer, and dense layers. The model uses the Adam optimizer and categorical cross-entropy loss for multiclass classification.

### 4.4 Model Training and Validation

The CNN model is trained using the prepared image dataset. Model checkpoints and early stopping are used during training, and validation data is used to monitor model performance.

### 4.5 Performance Visualization

Training and validation accuracy and loss are plotted to analyze the learning behavior and performance of the model.

### 4.6 Disease Category Prediction

The trained model accepts an input apple leaf image, preprocesses it, and generates a predicted class using the model's output probabilities.

## 5. Expected Outcome

The expected outcome is a trained CNN-based image classification model that predicts whether an apple leaf belongs to the healthy, rust, scab, or multiple diseases category.

The project demonstrates the application of image preprocessing, convolutional neural networks, supervised learning, model validation, and image-based prediction in the field of computer vision.
