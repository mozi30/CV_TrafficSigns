# Dataset – GTSRB

## Overview

The **German Traffic Sign Recognition Benchmark (GTSRB)** is a multi-class single-image classification challenge.

| Property | Value |
|----------|-------|
| Classes | 43 |
| Training images | ~39 209 |
| Test images | ~12 630 |
| Image sizes | Varying (approx. 15×15 to 250×250 px) |

---

## Download options

### Option A – torchvision (recommended, automatic)

The notebooks use `torchvision.datasets.GTSRB`, which downloads and extracts the dataset automatically on first run:

```python
from torchvision import datasets, transforms

train_dataset = datasets.GTSRB(
    root="./data",
    split="train",
    download=True,
    transform=transforms.ToTensor()
)
test_dataset = datasets.GTSRB(
    root="./data",
    split="test",
    download=True,
    transform=transforms.ToTensor()
)
```

This places the data under `data/gtsrb/`.

### Option B – Kaggle

1. Install the Kaggle CLI: `pip install kaggle`
2. Place your `kaggle.json` credentials in `~/.kaggle/`
3. Run:
   ```bash
   kaggle datasets download -d meowmeowmeowmeowmeow/gtsrb-german-traffic-sign -p data/ --unzip
   ```
4. Rename / reorganise the extracted folders to match the expected layout:
   ```
   data/
   ├── train/
   │   ├── 0/
   │   ├── 1/
   │   └── …
   └── test/
       ├── images/
       └── GT-final_test.csv
   ```

### Option C – Official website

Download from <https://benchmark.ini.rub.de/gtsrb_dataset.html>:

- `GTSRB_Final_Training_Images.zip` → extract to `data/train/`
- `GTSRB_Final_Test_Images.zip`    → extract to `data/test/images/`
- `GTSRB_Final_Test_GT.zip`        → extract to `data/test/`

---

## Notes

- The `data/` directory is excluded from version control (see `.gitignore`).  
- The notebooks always fall back to the torchvision auto-download if the local folders are not found.
