# Retinal Image Segmentation using Deep Learning

This project focuses on semantic segmentation of retinal images using three deep learning architectures: **U-Net**, **U-Net++**, and **Attention U-Net**. The goal was to accurately segment the vessels in retinal fundus images and compare the effectiveness of each model.

## 🧠 Models Used

- **U-Net**: A U-Net architecture where the encoder is replaced with a pretrained VGG16 model from ImageNet, allowing transfer learning and deeper feature extraction.
- **U-Net++**: A variation of U-Net with nested and dense skip connections, built on top of the same VGG16-based encoder structure.
- **Attention U-Net**: Based on the VGG16-encoder U-Net, with attention gates added in the decoder path to focus on relevant spatial features.

## 🏆 Best Model Performance

- The **U-Net** model performed the best with a **Dice coefficient of 87%** after training for 500 epochs.

## 📊 Results Visualization

![Results Graph](/images/Graph.png)  
*A graph comparing Dice coefficients across models over training epochs.*

## 📐 Data Preprocessing

- **Original Images**: RGB (3-channel) retinal images.
- **Resized Images**: Images were resized to a smaller dimension for faster training.
- **Label Adjustment**: Labels (masks) were converted from 3-channel to 1-channel (grayscale) binary masks for segmentation.

### Image Example: Original vs Resized Mask

| Retinal Image |
|---------------|
| <img src="/images/Retinal_img.png" width="300"/>|


| Original Image | One-channel Mask |
|----------------|------------------|
| <img src="/images/Actual.png" width="300"/> | <img src="/images/Resized_image.png" width="300"/> |

## 🧮 Dataset Conversion

- Resized images and labels were saved as **NumPy arrays** for efficient data loading.
- NumPy arrays were used to train the models with appropriate data generators and preprocessing.

## 🏋️ Training

- Each model was trained for **500 epochs**.
- Loss function: Dice Loss
- Optimizer: Adam
- Evaluation metric: Dice Coefficient
- Below image shows the predicted image by the Unet model (on an image from test set)
 ![Result](/images/unet_result.png)

## 📌 Conclusion

The segmentation task showed that even basic architectures like U-Net perform strongly when trained properly. Future work may involve incorporating more robust augmentations or trying transformer-based architectures.

---
