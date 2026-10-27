SMS-Spam-Detection-Framework-using-LSTM-DistilBERT-and-Adversarial-Threat-Analysis.
​
# Hybrid DistilBERT & LSTM Smishing Detection System

## 1. Project Overview
This project is an advanced AI-powered Smishing and SMS Spam detection system. It employs a sophisticated pipeline including data preprocessing, feature separation, synthetic data augmentation via Google Gemini, and a hybrid deep learning architecture for real-time threat classification.

## 2. Problem Statement
Smishing (SMS phishing) poses a significant cybersecurity threat through fraudulent links and urgent social engineering tactics. Standard keyword filters are insufficient. This project addresses the challenge by leveraging state-of-the-art transformer models (DistilBERT) and recurrent networks (LSTM) enhanced with synthetic data augmentation.

## 3. Dataset & Preprocessing
* *Feature Separation:* The dataset was meticulously structured by dividing features into text inputs, numeric features, and target output labels.
* *Data Splitting:* Data was split into training and testing sets, with 20% reserved strictly for validation and evaluation.
* *Synthetic Data Generation:* Google Gemini was utilized to generate synthetic data samples to handle data imbalance and improve model robustness.

## 4. Models Explored & Comparison
Multiple model architectures were built, trained, and rigorously compared:
1. *Model 1:* 

Hybrid LSTM +Dense Neural Network

Model Type: Hybrid LSTM + Dense neural network combining text sequences with selected numerical features.
Dataset: Original preprocessed SMS/Smishing dataset (N = 53,668 test samples).
Optimization: Compiled using the Adam optimizer with a learning rate of 0.001, binary cross-entropy loss, and Early Stopping (patience=3, monitored via val_loss).


2. *Model 2:* 

Model Name: Fine-Tuned DistilBERT Model (Transfer Learning)

Transfer Learning Concept: Transfer learning is a machine learning technique where a model developed for a task is reused as the starting point for a second task. In Natural Language Processing (NLP), this allows us to leverage pre-trained language models that already possess a deep understanding of grammar, semantics, and context from massive text corpora, fine-tuning them on our specific SMS/Smishing dataset with fewer resources and high accuracy.

DistilBERT Architecture: DistilBERT is a small, fast, cheap, and light Transformer model based on the BERT architecture. By using knowledge distillation during the pre-training phase, DistilBERT reduces the size of a BERT model by 40% while retaining 97% of its language capabilities and being 60% faster.

Model Advantages for Smishing Detection: Unlike traditional recurrent networks, the attention mechanism in DistilBERT captures complex contextual dependencies and subtle phishing patterns in text messages, making it highly effective for binary classification between safe and spam/smishing messages.


 
3. *Model 3:* Gemini-augmented DistilBERT model.

 Model Name: GenAI-Augmented DistilBERT Transfer Learning Model
Dataset: The updated GenAI-augmented dataset combining the original preprocessed SMS/Smishing data with  ∼900  targeted synthetic messages to improve boundary-case robustness.

Architecture & Optimization: Utilizes the same robust transformer backbone and numerical feature integration pipeline, fine-tuned with optimized hyperparameters to minimize false positives on transactional and operational alerts.

Performance Goal: Assess whether the synthetic data effectively reduces false positives, improves boundary-case classification, and enhances overall security metrics compared to the original baseline.


* *Final Selection:* Based on comparative performance, the *Gemini-augmented DistilBERT model* was selected as the final optimal model for deployment.

## 5. Technologies Used
* *Python* (Core programming language)
* *TensorFlow / Keras & KerasHub* (Deep learning framework)
* *DistilBERT & LSTM* (Neural network architectures)
* *Google Gemini* (Synthetic data augmentation)
* *Gradio* (Interactive web UI for deployment)
* *Google Colab* (Development and cloud execution environment)

## 6. Installation
To set up the project locally or in a notebook environment, install the required dependencies:
```bash
pip install tensorflow keras keras-hub gradio
