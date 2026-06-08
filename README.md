# PCB-AI

AI-powered computer vision system for PCB component inspection, polarity verification, and defect detection.

## Current Progress

- Dataset collection completed
- Dataset cleaning completed
- Capacitor polarity marker classification defined
- Data augmentation pipeline implemented
- Images labeled into:
  - Top
  - Right
  - Bottom
  - Left
- Stratified train/validation/test split created

## Dataset Statistics

Original images: 218

Cleaned images: 174

Labeled images: 159

Classes:
- Top: 46
- Left: 55
- Bottom: 33
- Right: 25

  ## Experiment Results

| Model | Validation Accuracy | Test Accuracy |
|---------|---------|---------|
| CNN | 68.75% | 81.25% |
| MobileNetV2 (Frozen) | 87.50% | 68.75% |
| MobileNetV2 (Fine-Tuned) | 68.75% | 75.00% |

### Key Findings

- Custom CNN achieved the best test accuracy.
- MobileNetV2 showed signs of overfitting due to limited dataset size.
- Fine-tuning improved MobileNetV2 test performance from 68.75% to 75.00%.
- Class imbalance affected performance, particularly for the Right class.

## Next Steps

- CNN implementation
- Model training
- Transfer learning using MobileNetV2
- Evaluation and confusion matrix analysis
