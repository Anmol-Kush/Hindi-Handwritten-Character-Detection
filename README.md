# SCDL, Separable Convolutional Deep Learning Model

A lightweight and efficient handwritten character recognition system built using a Separable Convolutional Neural Network.

## Overview

SCDL, Separable Convolutional Deep Learning, is a compact neural network architecture designed for handwritten character recognition.

The project provides an end to end workflow covering image preprocessing, dataset preparation, model training, evaluation, and prediction. It uses TensorFlow, OpenCV, and Flask.

The model uses depthwise separable convolutions to reduce the number of parameters and computational cost while maintaining strong classification performance.

## Key Features

* Separable CNN architecture for efficient feature extraction
* Custom image preprocessing pipeline including cropping, resizing, padding, and rotation
* TensorFlow data augmentation for improved generalization
* Optimized dataset loading using `AUTOTUNE`
* Separate training, validation, and test datasets
* Flask web application for real time character prediction
* Evaluation metrics and visualization outputs
* Confusion matrix, accuracy curves, and loss plots

## Project Structure

```text
SCDL/
│
├── app/
│   └── flask_app.py              # Flask web application
│
├── results/
│   └── evaluation_report.txt     # Evaluation metrics and results
│
├── src/
│   ├── preprocess.py             # Image preprocessing and normalization
│   ├── recognize.py              # Model prediction logic
│   ├── results.py                # Accuracy and loss visualization
│   ├── segment.py                # Image segmentation utilities
│   └── train_model.py            # Model training pipeline
│
├── README.md
└── requirements.txt
```

## Dataset Information

| Property           |          Value |
| ------------------ | -------------: |
| Total Classes      |             46 |
| Training Samples   |         62,560 |
| Validation Samples |         15,640 |
| Test Samples       |         13,800 |
| Image Size         | 32 × 32 pixels |

The dataset also contains samples labeled as `UNREADABLE`. These samples are removed during preprocessing.

## Installation

Clone the repository and install the required dependencies:

```bash
git clone <your_repository_link>
cd SCDL
pip install -r requirements.txt
```

## Usage

### 1. Train the Model

Run the training pipeline:

```bash
python src/train_model.py
```

### 2. Run the Flask Application

Start the web application:

```bash
python app/flask_app.py
```

The Flask application provides an interface for submitting character images and receiving model predictions.

## Model Performance

The model was evaluated using separate training, validation, and test datasets.

| Metric              |       Performance |
| ------------------- | ----------------: |
| Training Accuracy   |         97 to 99% |
| Validation Accuracy |         95 to 97% |
| Test Accuracy       | Approximately 95% |

The model achieved strong classification performance across the 46 character classes. The use of depthwise separable convolutions reduces model complexity while retaining effective feature extraction capabilities.

Evaluation outputs, including accuracy curves, loss plots, and the confusion matrix, are available in the `results/` directory.

> Replace the approximate values above with the exact values from `results/evaluation_report.txt` before publishing the repository.

## Prediction Workflow

The prediction pipeline follows these steps:

1. The input image is preprocessed using cropping, resizing, padding, and rotation.
2. The processed image is passed to the SCDL model.
3. Separable convolution blocks extract relevant visual features.
4. The final classification layer generates probabilities for all 46 classes.
5. The Flask application displays the predicted character and confidence score.

## Technologies Used

* Python
* TensorFlow / Keras
* OpenCV
* Flask
* NumPy
* Matplotlib

## Acknowledgements

* TensorFlow and Keras
* OpenCV
* Dataset creators
* Open source community and contributors

