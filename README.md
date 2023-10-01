# README for DPT Assignment 1 - Feature Implementation

## Feature 1: A More Comprehensive Metric

### Introduction

The data minimization method currently employs Accuracy as the metric to evaluate the performance of the student model. However, accuracy can be misleading when dealing with imbalanced datasets, which is a common scenario for sensitive data. In this update, I introduce a more comprehensive metric, ROC-AUC, to replace accuracy. This score assesses a model's ability to correctly identify positive and negative instances. The relevant code is found in the following sections:

- Lines 443-452
- Lines 483-493
- Lines 525-533


### Functionality

This feature is implemented using the `sklearn.metrics.roc_auc_score()` function.


### Usage Example

You can see the updated code in action in the notebook `/ai-privacy-toolkit-main/notebooks/minimization_diabetes_reg.ipynb`.

## Feature 2: XOREncryption

### Introduction

The XOREncryption feature is a valuable addition to the ai-privacy-toolkit project, specifically located at `/ai-privacy-toolkit-main/apt/minimization/minimizer.py`. The code for this feature spans from Line 29 to Line 121. This feature is encapsulated within the `XOREncryption` class, which implements a straightforward yet effective form of Homomorphic Encryption (HE) using XOR operations. It can encrypt data points of various types, including strings and floats, using two separate keys.

### Required library

!pip install struct

### Functionality

The `XOREncryption` class provides the following key functions:

- `float_to_fixed` and `fixed_to_float`: These are conversion functions for float data, allowing secure encryption and decryption. Float data is scaled into an int data by the inner parameter `precision`.

- `fixed_xor_encryption`: This function performs XOR encryption, intelligently handling both float and int data types. It performs XOR operations with the value and the key. The pre-input key is a random private int number recorded as the parameter `float_key`.

- `string_xor_encryption`: This function encrypts strings using XOR, extending the key for secure encryption. The pre-input key is a random private string recorded as the parameter `string_key`.

- `encrypt` and `decrypt`: These functions are used to encrypt input data for secure processing and retrieve the original data when needed. The `decrypt` function redoes the `encrypt` function on encrypted data.


### Usage Example

Usage examples are documented in the class comments and demonstrated in the notebook `/ai-privacy-toolkit-main/notebooks/minimization_diabetes_reg.ipynb`.