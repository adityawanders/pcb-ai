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

## Next Steps

- CNN implementation
- Model training
- Transfer learning using MobileNetV2
- Evaluation and confusion matrix analysis
