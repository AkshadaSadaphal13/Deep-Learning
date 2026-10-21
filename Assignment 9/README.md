# Assignment 9: Pre-trained ViT vs CNN for Image Classification

## Objective
Perform image classification using a pre-trained Vision Transformer (ViT) and compare its performance with a pre-trained CNN.

## Dataset
- **CIFAR-10**: 10 image classes.
- The notebook uses a reproducible subset of the training and test sets to keep runtime manageable.
- Images are resized to `224 × 224` and normalized using ImageNet statistics.

## Models
1. **ResNet-18 (CNN)** — ImageNet-pretrained convolutional model with a new 10-class classification layer.
2. **Vision Transformer (ViT)** — `google/vit-base-patch16-224-in21k` encoder with a new 10-class classification layer.

Both pretrained backbones are frozen; only the classification head is trained. This is a transfer-learning baseline, not full fine-tuning.

## Metrics
- Accuracy
- Macro precision
- Macro recall
- Macro F1-score
- Training time
- Confusion matrices and classification reports

## Files
- `Assignment_9_ViT_vs_CNN.ipynb` — complete notebook with explanations, code, plots, evaluation, and conclusion.
- `README.md` — assignment overview and execution guide.
- `requirements.txt` — Python dependencies.

## How to Run

### Option A: Google Colab
1. Upload `Assignment_9_ViT_vs_CNN.ipynb` to Google Colab.
2. Select **Runtime → Change runtime type → T4 GPU** (recommended, if available).
3. Run all cells from top to bottom.
4. The first run downloads CIFAR-10 and the pretrained model weights.

### Option B: VS Code
Use Python 3.10 or 3.11 in a virtual environment. A GPU is recommended; CPU execution can be very slow because images are resized to 224 × 224 and ViT is computationally intensive.

```bash
python -m venv .venv
```

Windows PowerShell:
```powershell
.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
```

Then open the notebook in VS Code and select the `.venv` Python kernel.

## Important Notes
- Internet access is required on the first run to download CIFAR-10 and pretrained weights.
- Adjust `TRAIN_SAMPLES`, `TEST_SAMPLES`, `BATCH_SIZE`, and `EPOCHS` in the notebook according to available memory and runtime.
- Actual metrics are produced when the notebook runs. Do not report placeholder or assumed scores.
- Output images (`training_curves.png` and `confusion_matrices.png`) are saved when the relevant cells run. Save/commit these generated images if your submission requires outputs.

## Expected Observations to Discuss
After execution, compare the displayed metrics and explain:
1. Which model has higher test accuracy in your run.
2. Differences in macro precision, recall, and F1-score.
3. Training-time differences on your hardware.
4. Which CIFAR-10 classes are most frequently confused.
5. Limitations of using a subset and frozen feature extractors.

## References
- CIFAR-10: https://www.cs.toronto.edu/~kriz/cifar.html
- ResNet paper: https://arxiv.org/abs/1512.03385
- Vision Transformer paper: https://arxiv.org/abs/2010.11929
- PyTorch: https://pytorch.org/docs/stable/index.html
- Torchvision: https://pytorch.org/vision/stable/index.html
- Hugging Face Transformers: https://huggingface.co/docs/transformers/index
