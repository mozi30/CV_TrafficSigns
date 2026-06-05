# CV_TrafficSigns

Analysis and comparison of different deep-learning models on the **GTSRB** (German Traffic Sign Recognition Benchmark) dataset.

## Project structure

```
CV_TrafficSigns/
├── data/
│   └── README.md          # Dataset download instructions
├── notebooks/
│   ├── 01_Data_Exploration.ipynb        # Dataset statistics & visualisations
│   ├── 02_CNN_from_scratch.ipynb        # Custom CNN trained from scratch
│   ├── 03_ResNet50_transfer_learning.ipynb   # ResNet-50 fine-tuning
│   ├── 04_MobileNetV2_transfer_learning.ipynb # MobileNetV2 fine-tuning
│   └── 05_Model_Comparison.ipynb        # Side-by-side metrics comparison
├── requirements.txt
└── README.md
```

## Dataset

The GTSRB dataset contains **51 839 images** across **43 traffic-sign classes**.  
Follow the instructions in [`data/README.md`](data/README.md) to download it.

The notebooks expect the following layout after downloading:

```
data/
├── train/
│   ├── 0/   ← class 0 images
│   ├── 1/
│   └── …
└── test/
    ├── images/
    └── GT-final_test.csv
```

## Models compared

| Notebook | Model | Strategy |
|----------|-------|----------|
| 02 | Custom CNN | Trained from scratch |
| 03 | ResNet-50 | Transfer learning (ImageNet → GTSRB) |
| 04 | MobileNetV2 | Transfer learning (ImageNet → GTSRB) |

## Quick start

```bash
# 1. Create and activate a virtual environment
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate

# 2. Install dependencies
pip install -r requirements.txt

# 3. Download the dataset (see data/README.md)

# 4. Launch Jupyter
jupyter notebook notebooks/
```

## Requirements

- Python ≥ 3.9
- See `requirements.txt` for the full list of packages.

