
# 🌟 3D Organ Segmentation Using VNet 🌟

## Overview
Welcome to the 3D Organ Segmentation project! This repository utilizes the **VNet** model to perform accurate segmentation of abdominal organs from 3D CT scans. Our goal is to enhance medical imaging analysis by precisely segmenting different organs in the abdomen.

## Setup Instructions
1. **Clone the Repository:**
   ```bash
   git clone https://github.com/Satyajithchary/3d-segmentation-model-on-ct-abdomen-organs.git
   cd 3d-segmentation-model-on-ct-abdomen-organs
   ```

2. **Set Up the Environment:**
   - Ensure you have Python 3.7 or higher installed.
   - Install the required packages:
     ```bash
     pip install -r requirements.txt
     ```
   - Alternatively, set up a Conda environment:
     ```bash
     conda create --name organ_segmentation python=3.8
     conda activate organ_segmentation
     pip install -r requirements.txt
     ```

3. **Download the Dataset:**
   - Obtain the dataset from the [CT Abdomen Organ Segmentation Dataset](https://zenodo.org/records/7860267) and place it in the `data` directory.

4. **Run the Code:**
   - Start training the model with:
     ```bash
     python train.py
     ```

## Model Architecture
The project employs the **VNet** architecture, a cutting-edge model for 3D image segmentation. Key features include:

- **Encoder-Decoder Structure:** Combines encoding and decoding layers with skip connections to capture both fine and coarse features.
- **3D Convolutions:** Processes volumetric data using 3D convolutions.
- **Residual Connections:** Improves network performance and training stability.

## Training Process
The training involves:

1. **Data Preprocessing:**
   - CT images and labels are resized to (256, 256, 128) and augmented to enhance model robustness.

2. **Training Procedure:**
   - Utilizes CrossEntropy loss.
   - Implements mixed precision training for efficient GPU usage.
   - Optimizer: Adam with a learning rate of 1e-4.

3. **Hyperparameters:**
   - **Batch Size:** 1
   - **Learning Rate:** 1e-4
   - **Number of Epochs:** 50

## Validation and Inference
Post-training, the model is evaluated using:

1. **Validation Metrics:**
   - **Dice Score:** Measures the overlap between predicted and actual segmentations.
   - Additional metrics include precision, recall, and accuracy.

2. **Inference:**
   - Model applies to unseen data, segmenting organs and evaluating performance using Dice score.

## 3D Visualization
- **Video Demonstration:** Includes a video of 3D rendered segments of predicted organs, available in the `visualization` directory.

## Note on GPU Constraints
Due to GPU memory constraints, the training process encountered limitations, and we were unable to generate results at this time. We are actively working to address these issues and will update the repository with results in the near future. 
