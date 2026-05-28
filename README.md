# GAN-MNIST-TensorFlow
A Deep Convolutional GAN (DCGAN) built with TensorFlow 2.x and Keras to generate synthetic MNIST handwritten digit images. Trained for 20 epochs using adversarial learning.
## Introduction

This project implements a Generative Adversarial Network (GAN) using TensorFlow 2.x and Keras API to generate handwritten digit images similar to the MNIST dataset.

GAN is a deep learning model that consists of two neural networks:

Generator
Discriminator

These two networks compete with each other during training.

The Generator tries to create fake handwritten digit images, while the Discriminator tries to identify whether the image is real or fake.

Over multiple training epochs, the Generator improves and produces realistic handwritten digits.

## Objective

The main objectives of this project are:

To understand the working of Generative Adversarial Networks (GANs)
To implement GAN using TensorFlow/Keras
To generate handwritten digit images similar to MNIST dataset
To visualize generated outputs during training
To analyze Generator and Discriminator losses
3. Technologies Used
Technology	Purpose
Python	Programming Language
TensorFlow 2.x	Deep Learning Framework
Keras API	Model Building
NumPy	Numerical Operations
Matplotlib	Visualization
Google Colab	Execution Environment

## Dataset Used
MNIST Dataset

The MNIST dataset contains:

70,000 handwritten digit images
Digits from 0–9
Image size: 28 × 28 pixels
Grayscale images

Dataset loaded using:

(x_train, _), (_, _) = tf.keras.datasets.mnist.load_data()
## Data Preprocessing

The following preprocessing steps were performed:

1. Normalization

Images were normalized from:

[0,255] → [-1,1]

Using:

x_train = (x_train.astype('float32') - 127.5) / 127.5
2. Reshaping

Images reshaped to:

(28, 28, 1)

## GAN Architecture
1 Generator Network

The Generator takes a random noise vector of size 100 and generates fake handwritten digit images.

Layers Used
Dense
BatchNormalization
LeakyReLU
Conv2DTranspose
Tanh Activation
Output
Generated image size: 28 × 28 × 1
2 Discriminator Network

The Discriminator classifies images as:

Real Image → 1
Fake Image → 0
Layers Used
Conv2D
LeakyReLU
Dropout
Flatten
Dense (Sigmoid)

## Loss Function

Binary Cross Entropy (BCE) loss function was used.

Generator Loss

Measures how successfully the Generator fools the Discriminator.

Discriminator Loss

Measures how accurately the Discriminator identifies real and fake images.

## Optimizer

Adam optimizer was used with:

Learning Rate = 0.0002
Beta1 = 0.5

## Training Process
The GAN model was trained for 20 epochs
Random noise vectors were given to the Generator
Fake images were generated
Discriminator compared real and fake images
Both networks updated continuously

During training:

Generated images were displayed
Loss values were tracked

## Output Generated

The model successfully generated handwritten digit images similar to the MNIST dataset.

Outputs included:

Generated digit image grids
Generator loss graph
Discriminator loss graph

## Results

After training:

The Generator learned to generate recognizable digits
Discriminator successfully differentiated real and fake images initially
Over time, Generator performance improved

Sample generated digits resembled:

0
1
2
3
4
7
9

 ## Challenges Faced

Some challenges during implementation included:
Balancing Generator and Discriminator training
Preventing unstable GAN training
Understanding loss fluctuations
Managing training time

## Conclusion

This project successfully implemented a Generative Adversarial Network using TensorFlow and Keras.
The Generator was able to create realistic handwritten digit images after training on the MNIST dataset.
The project improved understanding of:
Deep Learning
GAN Architecture
Adversarial Training
Image Generation

 ## Future Improvements

Future enhancements can include:

Training for more epochs
Using DCGAN architecture
Generating higher resolution images
Applying GANs for real-world image synthesis
Using Conditional GANs (CGAN)

## References
TensorFlow Official Documentation
Keras Documentation
MNIST Dataset Documentation
Ian Goodfellow – GAN Research Paper
Google Colab Documentation
