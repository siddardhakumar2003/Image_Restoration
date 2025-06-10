# 🖼️ Image Restoration Using DGUNet and Sparse Transform

This project implements an **Image Restoration Pipeline** that performs:

- **Image Deblurring** using **DGUNet** (Deep Gradient UNet)
- **Low-Light Enhancement** using **Sparse Transform-based Enhancement**

It is aimed at improving visual quality of degraded images for better aesthetics and further processing (e.g., computer vision tasks).

---

## 📌 Features

✅ Deblurring of motion-blurred or defocused images using DGUNet  
✅ Enhancement of underexposed/low-light images using sparse priors  
✅ Modular pipeline with intermediate and final outputs  
✅ Visual comparison and batch processing support

---

## 🧠 Methodology

### 1. Deblurring with DGUNet

DGUNet is a UNet-based architecture that integrates deep gradient priors to recover sharp details from blurred images. It is effective for both motion and defocus blur types. Key benefits:

- Gradient information guidance
- Edge-aware recovery
- Preserves fine textures
  
<img src="Architecture Images/DGUNET.png" width="100%"/>

### 2. Low-Light Enhancement with Sparse Transform

This method uses sparse representation in a transform domain to selectively amplify useful details in low-light regions while suppressing noise. It avoids overexposure and improves visibility without distorting color.

<img src="./Architecture%20Images/Sparse%20Transformers%20.png" width="100%"/>

---

## Results
  ### 1. Deblurring
| Input Image | Ground Truth | Final Enhanced Output |
|----------------|------------------|------------------------|
|<img src="./Input/Deblur/Garden.png" width="300"/> | <img src="./Ground_images/000022.png" width="300"/> | <img src="./output/Deblur/image (1).webp" width="300"/>|
|<img src="./Input/Deblur/Scenary.png" width="300"/> | <img src="./Ground_images/000222.png" width="300"/> | <img src="./output/Deblur/image (2).webp" width="300"/>|
<img src="./Input/Deblur/Spain.png" width="300"/> | <img src="./Ground_images/000085.png" width="300"/> | <img src="./output/Deblur/image (3).webp" width="300"/>|

### 2. Low Light Enhancement
| Input Image | Ground Truth | Final Enhanced Output |
|----------------|------------------|------------------------|
|<img src="./Input/Low_Light/1.png" width="300"/> | <img src="./Ground_images/1.png" width="300"/> | <img src="./output/Low_Light/image (4).webp" width="300"/>|
|<img src="./Input/Low_Light/179.png" width="300"/> | <img src="./Ground_images/179.png" width="300"/> | <img src="./output/Low_Light/image (5).webp" width="300"/>|
|<img src="./Input/Low_Light/669.png" width="300"/> | <img src="./Ground_images/669.png" width="300"/> | <img src="./output/Low_Light/image (6).webp" width="300"/>|
<img src="./Input/Low_Light/778.png" width="300"/> | <img src="./Ground_images/778.png" width="300"/> | <img src="./output/Low_Light/image (7).webp" width="300"/>|

---

## Evaluation of Models
Evaluation is based on Peak Signal-to-Noise Ratio (PSNR) and Structural Similarity Index (SSIM)—two standard metrics for assessing image quality.
CNN Network for Image Deblurring
### 1.The DGUNET model 
This model aims to restore sharp details from blurred images.<br/><br/>
•	**PSNR: 27.69 dB** – Indicates strong recovery of fine details and low reconstruction error.<br/>
•	**SSIM: 0.9089** – Suggests high structural similarity to the original sharp images.<br/><br/>
Interpretation:
These results demonstrate that the CNN model is highly effective at removing blur, preserving edges and textures with strong perceptual and numerical quality.
### 2. Sparse Transformer for Low-Light Enhancement
This model is designed to enhance visibility in poorly lit images.<br/><br/>
•	**PSNR: 19.46 dB** – Reflects reasonable restoration under difficult lighting conditions.<br/>
•	**SSIM: 0.82** – Indicates moderate structural preservation and perceptual enhancement.<br/><br/>
Interpretation:
The transformer enhances brightness and contrast effectively but shows some limitations in recovering fine details and reducing noise under extreme low-light scenarios.
Each model performs well within its domain:
•	The CNN excels at deblurring, offering high visual fidelity and sharp reconstruction.
•	The Sparse Transformer improves low-light visibility, though with slightly lower structural accuracy.
<div style={display:"inline"}>
<img src="./results/PSNR.png" width="33%" />
<img src="./results/Loss.png" width="33%" />
<img src="./results/SSIM.png" width="33%" />
</div>
