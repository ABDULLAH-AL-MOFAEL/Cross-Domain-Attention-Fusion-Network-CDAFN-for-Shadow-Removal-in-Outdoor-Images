# Shadow Removal using Cross-Domain Attention Fusion Network (CDAFN)

This project implements a novel architecture for outdoor shadow removal using a Cross-Domain Attention Fusion Network (CDAFN), compared against a baseline U-Net model on the ISTD dataset.

NB:This project is implemented entirely within a Colab notebook 


##  Features
- Novel attention mechanism combining RGB + shadow mask
- Encoder–decoder structure with attention fusion
- Evaluation on PSNR, SSIM, LPIPS, Precision, Recall, F1
- Visualizations and CSV metric exports

##  Dataset
We use the **ISTD dataset**, containing:
- Shadow Image (`*_A`)
- Shadow-Free Ground Truth (`*_B`)
- Binary Shadow Mask (`*_C`)

To automatically download in Colab:
```python
import kagglehub
path = kagglehub.dataset_download("sabarinathan/istd-dataset")
```

## Model Architectures
- `cdafn.py`: Our proposed CDAFN model with channel and spatial attention
- `unet.py`: Standard U-Net for baseline comparison

## Project Files
| File                     | Description                             |
|--------------------------|-----------------------------------------|
| `train_cdafn.py`         | Train the CDAFN model                   |
| `train_unet.py`          | Train the U-Net baseline model          |
| `evaluate.py`            | Evaluate both models                    |
| `cdafn_metrics.csv`      | CDAFN performance metrics               |
| `unet_metrics.csv`       | U-Net performance metrics               |
| `model_comparison_metrics.csv` | Combined CSV for bar plots         |

##Installation
Install the required packages:
```bash
pip install -r requirements.txt
```

##  Running
### Train CDAFN:
```bash
python train_cdafn.py
```

### Train U-Net:
```bash
python train_unet.py
```

### Evaluate:
```bash
python evaluate.py
```

## Results
Trained models achieve:

| Metric     | CDAFN ↑ | U-Net ↑ |
|------------|---------|---------|
| PSNR       | 23.90   | 18.42   |
| SSIM       | 0.91    | 0.81    |
| LPIPS ↓    | 0.139   | 0.281   |
| Precision  | 0.915   | 0.826   |
| Recall     | 0.948   | 0.865   |
| F1 Score   | 0.921   | 0.805   |

##  Citation
If you use this code or architecture, please cite the original ISTD dataset and credit this project.
