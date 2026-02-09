**Lab Assignment - 1:** Synthetic Image Data Generation & Classification

**Objective**
The objective of this lab is to help students understand synthetic data generation using a simple generative approach and implement it using Python. The assignment also aims to evaluate how effectively deep learning models can learn from synthetically generated data.

**Problem Statement**
- Generate synthetic image data for 40 different cat species
- Create 10 images per species, resulting in a dataset of 400 images
- Train and evaluate:
- A pre-trained ResNet model
- A custom CNN model
- Compare the classification accuracy of both models

**Dataset Description**
- Total Classes: 40 cat species
- Images per Class: 10
- Total Images: 400
- Data Type: Synthetic image data
- Image Format: RGB images
- Data Generation Method: Prompt-based generative image creation using a simple generative technique
- The generated images are organized in a class-wise folder structure, making them compatible with standard deep learning pipelines.

**Methodology**
1. Synthetic Data Generation
- A generative method was used to create realistic images of cats belonging to 40 distinct species.
- Each species was generated using a predefined list of class names.
- Images were automatically saved into class-specific directories for easy training and evaluation.

2. Model Training
🔹 Model 1: ResNet (Transfer Learning)
- A pre-trained ResNet model was used for classification.
- The final fully connected layer was modified to support 40 output classes.
- Transfer learning allowed the model to leverage pre-learned features for better performance on a small dataset.
🔹 Model 2: Custom CNN
- A custom Convolutional Neural Network was designed from scratch.
The model includes:
Convolutional layers
Activation functions
Pooling layers
Fully connected layers
- This model was trained solely on the generated dataset without any pre-trained weights.
3️⃣ Model Evaluation
- Both models were evaluated using classification accuracy.
- The dataset was split into training and testing sets.
- Accuracy results were compared to analyze:
- The effectiveness of transfer learning
- The performance of a custom model on synthetic data

**Results**
Model	Description	Accuracy
ResNet	Pre-trained transfer learning model	Higher accuracy
Custom CNN	Model trained from scratch	Lower accuracy compared to ResNet

The ResNet model achieved better accuracy due to its ability to reuse rich feature representations learned from large-scale datasets.

**Key Learnings**
- Synthetic data can be effectively used for training deep learning models.
- Transfer learning significantly improves performance when training data is limited.
- Custom models require more data to generalize well.
- Proper dataset organization is critical for model training.

**Technologies Used**
- Python
- PyTorch / TensorFlow (depending on implementation)
- ResNet Architecture
- Custom CNN
- NumPy

Matplotlib

Generative Image Model
