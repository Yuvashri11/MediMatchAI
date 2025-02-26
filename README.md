# MediMatchAI
#Problem Statement

In medical applications, users manually enter tablet names to place orders. This process is error-prone and time-consuming, especially when dealing with handwritten prescriptions. Misinterpretation of medicine names or dosages can lead to severe consequences, such as incorrect orders or health risks. The goal is to automate this process by allowing users to upload an image of a handwritten prescription, which will then be automatically converted to text using a highly precise handwriting recognition system.


# Solution Overview

This project utilizes a Convolutional Recurrent Neural Network (CRNN) with Connectionist Temporal Classification (CTC) loss to recognize and digitize handwritten prescriptions. CRNN combines CNN (for feature extraction) and RNN (for sequence modeling), making it well-suited for recognizing sequential patterns in handwriting. The model is trained on the IAM Handwriting Database and achieves high accuracy in text recognition.

# Dateset

IAM Handwriting Database 

MediPres Dataset

Dataset consists of handwritten text samples used for OCR model training.


# Model Architecture

**1. Feature Extraction (CNN)**

Convolutional Layers: Extracts spatial features from images.

MaxPooling Layers: Reduces dimensions while preserving key information.

**2. Sequential Modeling (RNN - LSTM)**

Recurrent Layers: Uses Bidirectional LSTM to process sequential features.

Dense Layer: Maps RNN outputs to character probabilities.

**3. CTC Loss Function**

Removes Alignment Dependency: Enables text recognition without pre-segmented characters.

Improves Prediction Accuracy: Corrects sequences based on probability distribution.



