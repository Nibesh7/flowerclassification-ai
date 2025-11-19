# Flower Classification

A small project for classifying flower species using deep learning.

## Features
- Train a convolutional neural network on a flower dataset.
- Evaluate model accuracy and visualize predictions.
- Simple CLI for training and inference.

## Quick start

1. Create a virtual environment and install dependencies:
```bash
python -m venv .venv
source .venv/bin/activate   # macOS / Linux
.venv\Scripts\activate      # Windows
pip install -r requirements.txt
```

2. Prepare data (example uses Oxford 102 Flowers or your own organized dataset):
```
data/
    train/
        daisy/
        dandelion/
        rose/
        sunflower/
        tulip/
    val/
    test/
```

3. Train:
```bash
python train.py --data data --epochs 20 --batch-size 32 --lr 1e-3
```

4. Evaluate:
```bash
python evaluate.py --model checkpoints/latest.pth --data data/test
```

5. Inference example:
```python
# inference.py
from model import load_model, predict
model = load_model("checkpoints/latest.pth")
print(predict(model, "examples/flower.jpg"))  # prints predicted label
```



## Project structure
- train.py         — training script
- evaluate.py      — evaluation script
- inference.py     — single-image prediction
- model.py         — model definition and utilities
- datasets.py      — data loading and augmentation
- requirements.txt — Python dependencies
- README.md

## Notes
- Replace model/data paths and hyperparameters to suit your environment.
- Use GPU for faster training if available.

## License
MIT License — see LICENSE file for details.