# Snapdocs Custom Modifications

## Custom Detection Heads
- **DualDetect** (models/yolo.py): Two-head detection architecture for ensemble predictions
- **DualDDetect** (models/yolo.py): Dual detection with depthwise separable convolutions
- **TripleDetect** (models/yolo.py): Three-head detection architecture

## Training Integration
- **train_dual.py**: MLflow integration with per-epoch metric logging
  - Train/val losses, mAP, precision, recall
  - Per-class mAP tracking
  - System metrics (GPU memory, learning rate)
  - tqdm-loggable support for structured CloudWatch logging
- **val_dual.py**: Validation logic for dual-head models
- **val_triple.py**: Validation logic for triple-head models

## Loss Functions
- **utils/loss_tal_dual.py**: Custom dual-head loss computation
- **utils/loss_tal_triple.py**: Triple-head loss computation

## Upstream
- Fork of: https://github.com/WongKinYiu/yolov9
- Custom branch: snapdocs-custom
- Merge strategy: Rebase snapdocs-custom on upstream updates

## Key Files Modified
- models/yolo.py (lines 127-248+)
- train_dual.py (lines 381-445 for MLflow)
- val_dual.py
- val_triple.py
- utils/loss_tal_dual.py
- utils/loss_tal_triple.py
