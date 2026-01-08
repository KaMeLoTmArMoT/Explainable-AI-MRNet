<div align="center">
  <h3 align="center">MRNet XAI</h3>

  <p align="center">
    Explainable deep learning for knee MRI classification on the MRNet dataset (CAM + SHAP) with an interactive viewer.
    <br />
    Train → generate explanations → inspect axial/coronal/sagittal slices side-by-side.
    <br /><br />
    <a href="https://stanfordmlgroup.github.io/competitions/mrnet/"><strong>MRNet Dataset »</strong></a>
    ·
    <a href="https://github.com/KaMeLoTmArMoT/mrnet_xai/issues">Report Bug</a>
    ·
    <a href="https://github.com/KaMeLoTmArMoT/mrnet_xai/issues">Request Feature</a>
  </p>
</div>

## About The Project

This repository contains scripts to train MRNet-style models and generate explainability artifacts (CAM/SHAP) for knee MRI exams. 
MRNet is a knee MRI dataset/competition with 1,370 exams from Stanford University Medical Center. 

<p align="center">
  <!-- Replace with your best screenshot (e.g. from images/TP.png) -->
  <img src="images/TP.png" width="640" alt="Viewer example (TP)">
</p>

## Key Features

- Training scripts for MRNet-style classification workflows (`train_mrnet.py`, `train_classifier.py`). 
- Generate CAM visualizations (`create_cams.py`). 
- Generate SHAP visualizations (`create_shaps.py`). 
- Interactive OpenCV-based viewer that shows CAM / raw slice / SHAP for axial, coronal, sagittal planes (`vis_predictions.py`). 
- Notebook included for experimentation (`MRNet_v1_0.ipynb`). 

## Built With

- PyTorch + TorchVision. 
- OpenCV, NumPy, Pandas, Matplotlib. 
- SHAP. 

## Getting Started

### Prerequisites

- Python environment (venv/conda recommended).
- MRNet dataset access (see Dataset section). 

### Installation

1. Clone:
   ```bash
   git clone https://github.com/KaMeLoTmArMoT/mrnet_xai.git
   cd mrnet_xai
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
   Note: requirements include a Git dependency (`torchsample`). 

## Dataset

- MRNet is distributed under a research-use agreement; the download link and dataset must not be redistributed. 
- Official info + registration: https://stanfordmlgroup.github.io/competitions/mrnet/ 

## Usage

### 1) Train a model
Start with the training scripts:
- `train_mrnet.py` 
- `train_classifier.py` 

### 2) Generate explanations
Use:
- `create_cams.py` for CAM outputs. 
- `create_shaps.py` for SHAP outputs. 

### 3) View predictions + explanations
Run the viewer:
- `vis_predictions.py` 

#### Viewer key bindings (current)

- Quit: `q` or `Esc`. 
- Change slice index (per plane):
  - Decrease: `1` (axial), `2` (coronal), `3` (sagittal). 
  - Increase: `7` (axial), `8` (coronal), `9` (sagittal). 
- Change case:
  - Prev/next: `4` / `6`. 
  - Jump to case: `Enter` then type case id (in console). 
- Switch SHAP source: `v` (if multiple sources exist). 
- Zoom: `+` / `-`, reset with `0`. 

## Examples

<p align="center">
  <img src="images/TP.png" width="350" alt="True Positive">
  <img src="images/TN.png" width="350" alt="True Negative">
</p>
<p align="center">
  <img src="images/FP.png" width="350" alt="False Positive">
  <img src="images/FN.png" width="350" alt="False Negative">
</p>

## Contributing

Contributions are welcome:
1. Fork the repo
2. Create a feature branch
3. Open a PR

## License

