# Synthetic_Brain_Image_Generation
Generating synthetic images through Generative Adversarial
Networks allows researchers to create realistic, diverse MRI
images that can supplement or expand existing datasets
without needing additional patient scans.

This synthetic data can be used for training machine learning models, thus improving the reliability and robustness of AI-driven diagnostics.
## Project Motivation
- **Data Scarcity:**  MRI data is limited due to privacy, cost, and patient availability.
- **Augmentation Needs:**  High-quality data is needed for effective machine learning models in healthcare.

**Impact:** Synthesized data can improve the reliability of medical AI applications.

## Project Goals
- **Enhance Data Availability:**  Provide more MRI data for AI research.
- **Improve Research and Diagnostics:**  Supplement scarce MRI datasets with high-quality synthetic images.

**Long-Term Impact:**  Develop more accurate medical AI systems with synthetic data support.

## Applications in Medical Imaging
- **Data Augmentation:** Generated images supplement datasets for model training.
- **Diagnostic Tool Training:** Enhances accuracy of AI models used for diagnostics.
- **Privacy-Safe Research:** Synthetic data is free from patient privacy constraints.

## Model : Deep Convolutional Generative Adversarial Network (DCGAN)
Consists of two parts – a Generator and a Discriminator.
- **Generator:** Creates synthetic images.
- **Discriminator:** Determines if an image is real or fake.

**Training Goal:** Generator produces images that the Discriminator cannot distinguish from real ones.                                                                                                               
**Outcome:** As they improve, the synthetic images become more realistic.
## Generator Model
![image](https://github.com/user-attachments/assets/b05bc906-414b-49e6-ab29-74d7d3997b48)

- **Structure:** Starts with a latent vector, transforms through up-sampling layers.
- **Layers:** Four transposed convolutional layers to increase image resolution.
- **Batch Normalization:** Stabilizes learning and speeds up training.
- **Activation:** Uses Tanh as the final layer to normalize output between -1 and 1.
- **Output:** Generates 64x64 pixel MRI images.
  
## Discriminator model
![image](https://github.com/user-attachments/assets/7bc7b1b2-69f0-409f-99bd-a4ceb85ff4c2)

- **Role:** Identifies if an input is real or synthetic.
- **Structure:** Four convolutional layers that down-sample the image.
- **Batch Normalization:** Added after each layer to stabilize training.
- **Activation:** Uses Sigmoid function. LeakyReLU for robust feature extraction. 
- **Output:** Single probability score, indicating whether the image is real or fake.
  
## Model Architecture


![image](https://github.com/user-attachments/assets/391cebe0-3f95-4a58-8e1a-fa238796551c)

**DCGAN (Deep Convolutional GAN)** was chosen for this project due to its ability to generate high-quality images.

- **Components:**  Convolutional layers in both Generator and Discriminator.
- **Latent Space:**  Random noise is converted into images through the Generator.
- **Activation Functions:**  ReLU in Generator, LeakyReLU in Discriminator.
- **Key Parameters:**  Learning rate = 0.0002,  Batch size = 128,   Epochs = 25.
  

## Dataset overview
- **Source:** Kaggle's MRI dataset repository ('brain-mri-images’).
- **Details:** 14,715 MRI slices, various brain regions and orientations.
- **Permissions:** Dataset is open-source under Apache 2.0 license, suitable for research.
  
  
## Pre-processing of MRI images

![image](https://github.com/user-attachments/assets/18c110ee-e5da-4379-9fd7-9f4541a8848f)

## Comparison 

![image](https://github.com/user-attachments/assets/6e181c79-bbd8-4c42-bf00-7ea2bf55cf6e)
## Training Process
- **Steps:** Alternating training between Generator and Discriminator with real and fake images.
- **Epochs:** 25 epochs, allowing the model to learn complex image features.
- **GPU Use:** Model training on GPU (Google Colab) for efficiency.
- **Goal:** Minimize loss for both networks while enhancing image realism.
  
## Generated Image Samples

**Synthetic MRI images generatedat various training stages-**

![image](https://github.com/user-attachments/assets/14352e66-2ff1-440f-9789-9f8c2fa870c6)
## Visual Comparison
![image](https://github.com/user-attachments/assets/b43e1699-4b31-47da-94ec-5cfdea6925a8)
## Results and Analysis
- **Training Metrics:**

**Generator Loss:** Improvements over epochs.(The loss is decreasing)
![image](https://github.com/user-attachments/assets/f628741b-27cc-4877-9870-9b3db7b30e5b)
## Challenges faced
- **GPU Limitations:** This project ran out of limits on GPU usage,which caused interruptions in training.This made it challenging to maintain steady progress.
- **Limited No. of epochs:** Due to resources constraints the model could only be trained for a limited number of epochs(training cycle).

**Impact:  Learning Quality**
With fewer epochs, the model didn’t reach its full potential for creating highly realistic images.
## Future Work
- **Enhancements :** Explore advanced GAN architectures like StyleGan , Progressive Gans...
- Increase dataset size and diversity for more robust training.
- Increase training epoch which was not possible due to resourse limitations.
- **New applications :** Apply methods to other imaging types like CT or Ultrasound.
