# 360-Degree Video Super-Resolution

<div align="center">

[![Python](https://img.shields.io/badge/Python-3.9+-3776ab?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/downloads/)
[![OpenCV](https://img.shields.io/badge/OpenCV-4.x-c90076?style=for-the-badge&logo=opencv&logoColor=white)](https://opencv.org/)
[![Pytorch](https://img.shields.io/badge/Pytorch-1.13.1-5c3ee8?style=for-the-badge&logo=opencv&logoColor=white)](https://pytorch.org/)
[![Torchvision](https://img.shields.io/badge/Torchvision-0.13.1-38761d?style=for-the-badge&logo=opencv&logoColor=white)](https://pypi.org/project/torchvision/)
[![basicsr](https://img.shields.io/badge/basicsr-1.4.2-b45f06?style=for-the-badge&logo=opencv&logoColor=white)](https://pypi.org/project/basicsr/1.3.4.0/)
[![facexlib](https://img.shields.io/badge/facexlib-0.3.0-cc0000?style=for-the-badge&logo=opencv&logoColor=white)](https://github.com/xinntao/facexlib)
[![gfpgan](https://img.shields.io/badge/gfpgan-1.3.8-f1c232?style=for-the-badge&logo=opencv&logoColor=white)](https://github.com/TencentARC/GFPGAN)



</div>

A powerful AI-driven solution for enhancing 360-degree videos using Real-ESRGAN and GFPGAN technologies. This project combines advanced super-resolution techniques with intelligent face enhancement to dramatically improve the quality of 360-degree video content.

![Screenshot 2025-06-05 144314](https://github.com/user-attachments/assets/aa08b953-795b-42c5-871e-d79bce56bd13)

##  Features

- **4x Super-Resolution**: Upscale 360-degree videos to 4 times their original resolution
- **AI-Powered Face Enhancement**: Intelligent face detection and enhancement using GFPGAN
- **Smart Blending**: Advanced blending algorithms for seamless results
- **Batch Processing**: Process multiple frames efficiently
- **Audio Preservation**: Maintains original audio quality during enhancement
- **Google Colab Ready**: Pre-configured Jupyter notebook for easy cloud execution

##  Quick Start

### Option 1: Google Colab (Recommended)
1. Open the `Real_ESRGAN_Video.ipynb` notebook in Google Colab
2. Run all cells in sequence
3. Upload your 360-degree video when prompted
4. Download the enhanced result

### Option 2: Local Installation
```bash
# Clone the repository
git clone https://github.com/WWIIITT/360-degree-video-super-resolution.git
cd 360-degree-video-super-resolution

# Install dependencies
pip install -r requirements.txt

# Run the enhancement script
python real_esrgan_video.py
```

##  Requirements
Python: 3.9 or higher, 
GPU: CUDA-compatible GPU recommended for faster processing, 
Dependencies:

- torch==1.13.1
- torchvision==0.13.1
- numpy==1.23.5
- basicsr==1.4.2
- facexlib==0.3.0
- gfpgan==1.3.8

##  Installation
### Automatic Setup (Google Colab)
The Jupyter notebook automatically handles all installations and dependencies.

### Manual Setup
```bash

# Install PyTorch (adjust CUDA version as needed)
pip install torch==1.13.1 torchvision==0.13.1

# Install required packages
pip install numpy==1.23.5
pip install basicsr==1.4.2 facexlib==0.3.0 gfpgan==1.3.8

# Install OpenCV
pip install opencv-python opencv-contrib-python

# Clone Real-ESRGAN
git clone https://github.com/xinntao/Real-ESRGAN.git
cd Real-ESRGAN
python setup.py install

# Clone GFPGAN
git clone https://github.com/TencentARC/GFPGAN.git
cd GFPGAN
python setup.py install
```
##  Usage
### Basic Usage
```bash
# Import required modules
from real_esrgan_video import enhance_360_video

# Enhance your 360-degree video
enhanced_video = enhance_360_video(
    input_path="your_360_video.mp4",
    output_path="enhanced_360_video.mp4",
    scale_factor=4
)
```

### Advanced Configuration
```bash
# Customize enhancement parameters
enhanced_video = enhance_360_video(
    input_path="input.mp4",
    output_path="output.mp4",
    scale_factor=4,
    face_enhance=True,
    gfpgan_weight=0.2,
    blur_kernel_size=151,
    blending_alpha=0.3
)
```

##  Technical Details
### Processing Pipeline
1. Frame Extraction: Extract individual frames from input video
2. Super-Resolution: Apply Real-ESRGAN for 4x upscaling
3. Face Detection: Identify faces using Haar cascades
4. Face Enhancement: Apply GFPGAN to detected face regions
5. Smart Blending: Seamlessly blend enhanced faces with upscaled background
6. Post-Processing: Apply CLAHE and noise reduction
7. Video Reconstruction: Reassemble frames with original audio

### Supported Formats
- Input: MP4, AVI, MOV, MKV, INSV (360-degree formats)
- Output: MP4 with H.264 encoding
- Audio: AAC encoding at 192kbps

##  Acknowledgments
- Real-ESRGAN by Xintao Wang et al.
- GFPGAN by Tencent ARC Lab
- BasicSR for the super-resolution framework
