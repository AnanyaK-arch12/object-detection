# MNIST Digit Classification and Localization

A deep learning project that combines **image classification and object localization** using a Convolutional Neural Network (CNN) built with TensorFlow and Keras.

The model identifies handwritten digits from the MNIST dataset and predicts the bounding box coordinates of each digit in a larger image.

## Project Overview

Traditional image classification identifies what is present in an image. Object localization goes a step further by predicting where the object is located.

This project demonstrates both tasks using a multi-output CNN.

### Key Features

* Handwritten digit classification for digits 0–9.
* Bounding box regression for digit localization.
* CNN-based feature extraction.
* Image preprocessing and padding.
* Model training and validation.
* Intersection over Union (IoU) calculation.
* Visualization of predicted and actual bounding boxes.
* Training metric plots for classification and localization.

## Technologies Used

* Python
* TensorFlow
* Keras
* TensorFlow Datasets
* NumPy
* Matplotlib
* Pillow
* Jupyter Notebook

## Model Architecture

The model uses a shared CNN feature extractor with two output branches.

**Feature extraction**

* Convolutional layer with 16 filters and ReLU activation.
* Average pooling.
* Convolutional layer with 32 filters and ReLU activation.
* Average pooling.
* Convolutional layer with 16 filters and ReLU activation.
* Average pooling.

**Dense layer**

* Flatten layer.
* Dense layer with 128 units and ReLU activation.

**Output branches**

* Classification: 10 units with softmax activation.
* Bounding box regression: 4 output values representing the bounding box coordinates.

The model is compiled with the Adam optimizer, categorical cross-entropy for classification, and mean squared error for bounding box regression.

## Dataset and Preprocessing

The project uses the **MNIST dataset**, loaded using TensorFlow Datasets.

Each 28 × 28 grayscale digit image is:

1. Padded to a 75 × 75 image.
2. Placed at a randomly generated position.
3. Normalized to a pixel range of 0 to 1.
4. Assigned a corresponding one-hot encoded digit label and bounding box coordinates.

No separate dataset download is required because the notebook loads MNIST through TensorFlow Datasets.

## Training

The notebook uses the following training configuration:

* Batch size: 64
* Epochs: 20
* Optimizer: Adam
* Classification loss: Categorical cross-entropy
* Localization loss: Mean squared error

It tracks classification accuracy, classification loss, and bounding box regression loss.

**Note:** The current notebook uses the MNIST training split for both its training and validation datasets. The validation results therefore should not be treated as independent test performance.

## Evaluation and Visualization

The notebook includes:

* Classification accuracy evaluation.
* Bounding box mean squared error.
* Intersection over Union (IoU) calculation.
* Plots of training and validation metrics.
* Visual comparison of predicted and actual bounding boxes.

## How to Run

### 1. Clone the repository

```bash
git clone https://github.com/AnanyaK-arch12/object-detection.git
cd object-detection
```

### 2. Install dependencies

```bash
pip install tensorflow tensorflow-datasets numpy matplotlib pillow jupyter
```

### 3. Launch Jupyter Notebook

```bash
jupyter notebook
```

### 4. Run the notebook

Open `Object_Detection.ipynb` and execute the cells in order.

The notebook downloads MNIST through TensorFlow Datasets when needed. An internet connection may be required for the initial dataset download.

## Project Structure

```text
object-detection/
│
├── Object_Detection.ipynb
├── .gitignore
└── README.md
```

## Learning Outcomes

Through this project, I explored:

* CNN architecture and feature extraction.
* Multi-output neural networks.
* Image classification and object localization.
* Bounding box coordinate prediction.
* Regression and classification losses.
* IoU as a localization evaluation metric.
* Visualization of model predictions.

## Future Improvements

* Evaluate on a separate test dataset.
* Experiment with different CNN architectures.
* Improve bounding box prediction accuracy.
* Extend the approach to more complex images and multiple objects.
* Save and load the trained model for inference.

---

**Author:** Ananya K.
**Project:** MNIST Digit Classification and Localization
