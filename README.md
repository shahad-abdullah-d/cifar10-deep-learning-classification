# CIFAR-10 Image Classification Using Deep Learning

A deep learning project focused on classifying images from the CIFAR-10 dataset using fully connected neural networks. The project explores how network architecture, hyperparameters, and regularization techniques affect image classification performance.

## Project Overview

The goal of this project is to build and evaluate a neural network that predicts which of 10 categories an image belongs to.

The project follows an experimental workflow, starting with a baseline model, comparing different network architectures, tuning hyperparameters, and evaluating a final optimized model on unseen test data.

**Note:** This project uses fully connected Dense Neural Networks, not Convolutional Neural Networks (CNNs).

## Dataset

The project uses the CIFAR-10 dataset, which contains 60,000 color images across 10 classes:

- Airplane
- Automobile
- Bird
- Cat
- Deer
- Dog
- Frog
- Horse
- Ship
- Truck

Each image has a resolution of 32 × 32 pixels with 3 color channels.

## Tools and Libraries

- Python
- TensorFlow / Keras
- NumPy and Pandas
- Matplotlib
- Scikit-learn
- Jupyter Notebook / Google Colab

## Project Workflow

### 1. Data Preprocessing

- Loaded the CIFAR-10 dataset.
- Normalized pixel values to the range [0, 1].
- Flattened each 32 × 32 × 3 image into a vector of 3,072 features.
- Prepared training, validation, and test datasets.

### 2. Baseline Model

Built a fully connected neural network with one hidden Dense layer containing 128 neurons and a Softmax output layer for 10-class classification.

### 3. Architecture Experiments

Compared three network architectures while keeping the main training hyperparameters fixed:

| Architecture | Hidden Layers | Best Validation Accuracy |
|---|---:|---:|
| Shallow Network | 1 | 45.32% |
| Medium Network | 3 | 47.10% |
| Deep Network | 5 | 47.34% |

The experiments showed that increasing network depth produced only modest improvements in validation accuracy. The learning curves also indicated overfitting.

### 4. Hyperparameter Tuning

Experimented with different training configurations, including:

- Learning rates
- Batch sizes
- Optimizers
- Network architectures

### 5. Regularization Experiments

Investigated techniques to improve generalization:

- Dropout
- L2 Regularization
- Early Stopping
- Batch Normalization

Early Stopping was selected for the final model based on the experimental results.

### 6. Final Model

The final model uses a fully connected network with three hidden layers:

`3072 → 512 → 256 → 128 → 10`

- Architecture: Medium Dense Neural Network
- Trainable parameters: 1,738,890
- Output activation: Softmax
- Regularization technique selected: Early Stopping

## Final Model Results

The final model achieved the following results:

| Metric | Result |
|---|---:|
| Best Validation Accuracy | 49.98% |
| **Test Accuracy** | **49.62%** |
| Test Loss | 1.4501 |
| Macro Precision | 50.99% |
| Macro Recall | 49.62% |
| Macro F1-score | 49.48% |

The final model correctly classified **4,962 out of 10,000 test images**.

### Classification Performance

The model was evaluated using a confusion matrix and a classification report to examine its performance across the 10 image categories.

The results showed that classification performance varied by category, highlighting the limitations of using fully connected networks for image data.

## Key Learnings

- Increasing the number of hidden layers does not necessarily produce large improvements in validation accuracy.
- Overfitting can occur when training accuracy continues to improve while validation performance stops improving.
- Hyperparameter tuning and regularization can help improve model generalization.
- Flattening an image removes its original two-dimensional spatial structure, limiting the ability of Dense Neural Networks to learn spatial image patterns.

A possible future improvement is to explore Convolutional Neural Networks (CNNs), which are designed to learn spatial features from images.

## Project Files

- `CIFAR10_Deep_Learning_Classification.ipynb` — Complete notebook containing preprocessing, model training, architecture experiments, hyperparameter tuning, evaluation, and error analysis.

The CIFAR-10 dataset is loaded through TensorFlow/Keras and does not need to be uploaded separately.

## How to Run

1. Download the notebook from this repository.
2. Open it in Google Colab or Jupyter Notebook.
3. Install the required Python libraries if they are not already available.
4. Run the notebook cells in order to reproduce the experiments and results.

Training the different network architectures and running the tuning experiments may take some time.

## Author

Shahad Abdullah

Artificial Intelligence Bootcamp — Deep Learning Capstone Project
