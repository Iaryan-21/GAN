# Generative Adversarial Networks

Generative Adversarial Networks (GANs) are a class of machine learning frameworks designed by Ian Goodfellow and his colleagues in 2014. They consist of two neural networks, a Generator and a Discriminator, which compete against each other in a game-theoretic scenario. The Generator tries to create data that is indistinguishable from real data, while the Discriminator tries to distinguish between real and generated data. This adversarial process drives both networks to improve their capabilities, resulting in the Generator producing highly realistic data.


### Datasets

**MNIST Number Dataset**:

- The MNIST dataset contains 70,000 images of handwritten digits (0-9) in grayscale, each of size 28x28 pixels. It is commonly used for training and testing in the field of machine learning and computer vision.

**Summer to Winter Yosemite Dataset**:

- The Summer to Winter Yosemite dataset consists of images of Yosemite National Park captured in summer and winter. This dataset is used for image-to-image translation tasks, where the goal is to transform a summer scene into a winter scene and vice versa.

**Celeb A dataset**:
- The CelebA dataset contains over 200,000 celebrity images with 40 attribute annotations per image, spanning various poses and backgrounds. It is widely used for tasks like facial attribute recognition, face generation, and identity-based applications.


### CYCLE GAN

<p align="center">
  <img src="https://github.com/Iaryan-21/GAN/blob/main/assets/CycleGAN.webp" alt="Cycle GAN" width="400"/>
</p>

The CycleGAN consists of two main parts: the Generators (CycleGenerator) and the Discriminators.

**Generators**:
- There are two generators: \( G \) (transforms images from domain X to domain Y) and \( F \) (transforms images from domain Y to domain X).
  
**Encoder Part of Generators**:
- The encoder part of the CycleGenerator uses a series of ConvBlocks to progressively reduce the spatial dimensions of the input image while increasing the number of feature channels.
  
**ConvBlocks**:
- Each ConvBlock consists of a convolutional layer followed by batch normalization (optional) and a ReLU activation function (optional).
  
**ResNet Part of Generators**:
- The central part of the CycleGenerator uses a series of ResidualBlocks. Each ResidualBlock consists of two ConvBlocks and includes a skip connection that adds the input to the output of the block.
  
**Decoder Part of Generators**:
- The decoder part of the CycleGenerator uses DeconvBlocks (deconvolutional layers) to progressively increase the spatial dimensions of the feature maps while reducing the number of feature channels back to that of the input image.
  
**DeconvBlocks**:
- Each DeconvBlock consists of a ConvTranspose2d layer followed by batch normalization (optional) and a ReLU activation function (optional).
  
**Final Layer of Generators**:
- The last layer of the CycleGenerator is a ConvTranspose2d layer followed by a Tanh activation function to produce the final output image.
  
**Discriminators**:
- There are two discriminators: \( D_X \) (distinguishes between real images from domain X and fake images generated by \( F \)) and \( D_Y \) (distinguishes between real images from domain Y and fake images generated by \( G \)).
  
**Discriminator Architecture**:
- Each discriminator consists of a series of ConvBlocks with increasing feature dimensions. The last ConvBlock produces a single output value indicating whether the input image is real or fake.

### DEEP CONVOLUTION GAN

<p align="center">
  <img src="https://github.com/Iaryan-21/GAN/blob/main/assets/DC_GAN.webp" alt="Deep Convolution GAN" width="400"/>
</p>

The DCGAN consists of two main parts: the Generator and the Discriminator.

**Discriminator**:

- The Discriminator takes an input image, which is flattened into a 1D vector.
- The flattened image is passed through the first fully connected layer.
- A LeakyReLU activation function is applied to the output of the first fully connected layer.
- A dropout layer is applied to the activated output to prevent overfitting.
- The process is repeated for the second and third fully connected layers, each followed by a LeakyReLU activation and dropout layer.
- The last fully connected layer produces a single output value indicating whether the input image is real or fake.

**Generator**:

- The Generator starts with a latent vector (random noise) as input.
- The latent vector is passed through the first fully connected layer, followed by a LeakyReLU activation.
- The process continues with the second and third fully connected layers, each followed by a LeakyReLU activation, progressively increasing the size of the output.
- The final fully connected layer produces the generated image, which is activated by a Tanh function to scale pixel values between -1 and 1.

### Output
1. Cycle GAN (Yosemite Dataset)
![Cycle GAN OPT](https://github.com/Iaryan-21/GAN/blob/main/assets/cycle_gan_opt.png)

2. DC GAN (MNIST Dataset)
![DC GAN OPT](https://github.com/Iaryan-21/GAN/blob/main/assets/DC_GAN_opt.png)

### Reference

- https://arxiv.org/pdf/1703.10593
- https://arxiv.org/pdf/1511.06434
