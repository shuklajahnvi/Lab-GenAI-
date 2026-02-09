**Objective**
The objective of this lab is to design, implement, and train a basic Generative Adversarial Network (GAN) capable of generating synthetic images for multiple datasets. Students will train and evaluate the GAN on both MNIST and Fashion-MNIST datasets and analyze the quality of generated images over training epochs.

**Problem Context**
A university’s digital archive server has partially crashed, resulting in missing scanned images of different types. To test the AI pipeline end-to-end before data recovery, synthetic image generation is required.
In this lab, a single GAN framework is designed to generate realistic images for two different image domains, demonstrating the model’s adaptability.

**Datasets Used**
- The GAN is trained and evaluated on both of the following datasets:
- MNIST – Handwritten digit images
- Fashion-MNIST – Clothing item images
- Both datasets are loaded using:
- TensorFlow / Keras, or
- PyTorch / Torchvision dataset utilities
- All images are normalized appropriately before training.

**⚙️ Input Parameters**

The program supports configurable inputs for each dataset:

Parameter	Description
dataset_choice	Dataset selection (mnist or fashion)
epochs	Number of training epochs
batch_size	Batch size
noise_dim	Dimension of noise vector
learning_rate	Learning rate
save_interval	Epoch interval for saving samples

The same GAN architecture is reused for both datasets with dataset-specific training runs.

**Methodology**
_1.Generator Network_

- Converts random noise vectors into synthetic images
- Output shape dynamically adapts to the dataset image size
- Trained to fool the discriminator

_2.Discriminator Network_

- Classifies images as real or fake
- Trained on both real dataset images and generated images
- Outputs authenticity probability

_3.GAN Training_

Alternating training of Generator and Discriminator
Separate training runs for:

- MNIST
- Fashion-MNIST

Loss functions computed for both networks
Epoch-wise training logs printed

_4.Image Generation & Saving_

- Generated images saved at fixed intervals
- Each saved image contains a 5×5 grid (25 samples)
- Final training generates 100 synthetic images per dataset

_5️.Evaluation Using Transfer Learning_

- A pre-trained classifier model is used to:
- Predict labels of generated MNIST images
- Predict labels of generated Fashion-MNIST images
- Label distributions are analyzed to assess realism and diversity

**Expected Outputs**
_Output 1:_ Training Logs

Printed separately for both datasets:
Epoch 10/50 | D_loss: 0.53 | D_acc: 78.12% | G_loss: 1.24

_Output 2:_ Generated Samples

Folders created:

generated_samples/
├── mnist/
│   ├── epoch_05.png
│   └── epoch_10.png
└── fashion_mnist/
    ├── epoch_05.png
    └── epoch_10.png

_Output 3:_ Final Generated Images
final_generated_images/
├── mnist/
│   └── 100 images
└── fashion_mnist/
    └── 100 images

_Output 4:_ Label Prediction Results

Predicted labels for both MNIST and Fashion-MNIST generated images
Class distribution reported separately for each dataset

**Technologies Used**

Python
TensorFlow / PyTorch
GAN Architecture
Transfer Learning
NumPy
Matplotlib

**Project Structure**
├── generated_samples/
│   ├── mnist/
│   └── fashion_mnist/
├── final_generated_images/
│   ├── mnist/
│   └── fashion_mnist/
├── gan_model.py
├── train_gan.py
├── evaluate_generated_images.py
├── requirements.txt
└── README.md

**Conclusion**
This lab demonstrates how a single GAN architecture can be trained on multiple datasets to generate domain-specific synthetic images. The results highlight the flexibility of GANs and the importance of training dynamics in producing realistic samples. Evaluation using pre-trained classifiers further validates the quality of generated images.
