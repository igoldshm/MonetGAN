# MonetGAN - Monet-Style Painting Generation
This repository contains an implementation of a Generative Adversarial Network (GAN) aimed at transforming photos into Monet-style paintings. The model was developed for the MonetGAN challenge on Kaggle.
The goal of the challenge was to use a GAN to take input photos and generate Monet-style paintings. The challenge serves as an excellent introduction to GANs and image-to-image translation tasks.
## Installation
- Python 3.x
- PyTorch 1.x
- torchvision
- tqdm
- matplotlib
- Pillow

To install the dependencies, you can create a virtual environment and install the requirements using the following command:
```bash
pip install -r requirements.txt
```
### Clone the Repository
```bash
git clone https://github.com/igoldshm/MonetGAN
```
## Model
In this project we used CycleGAN as our base architecture.
### Generator  implementation
### Discriminator  implementation
### Loss calculation
#### Generator loss
The generator loss is the sum of three different losses:
- Adversarial loss - the aim of the generator is to fool the discrimnator -> pred(fake monet)=1 (MSELoss)
- Identity loss - Monet → Monet should remain unchanged (L1Loss)
- Cycle Consistency Loss - Loss for reconstructing photo from fake Monet. Real → Monet → Real (L1Loss)
#### Discriminator loss
The discriminator loss is the adversarial loss - pred(fake monet)=0 (MSELoss)
## Training
- Generator optimizer: Adam
- Discriminator optimizer: Adam
- Learning rate: 0.0002
- Epochs = 100
- LAMBDA_CYCLE = 1  # Weight for cycle consistency loss
- LAMBDA_IDENTITY = 1  # Weight for identity loss

## License
This project is licensed under the MIT License.
## Acknowledgments
- The CycleGAN model is based on the paper Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks (https://arxiv.org/abs/1703.10593).
- Special thanks to the contributors of the PyTorch library and other open-source tools that made this project possible.
- Thanks to the MonetGAN challenge on Kaggle for providing an engaging way to learn and experiment with GANs

