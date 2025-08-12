# Analysis Report

## Summary

- Model loaded from: `best_model_Nadam.h5`

- NUM_CLASSES (Caltech-101): 102

- Image size used: (32, 32)

- Train accuracy (after all phases): 0.2848

- Validation accuracy (after all phases): 0.1928

- Test accuracy (after all phases): 0.2108


## Macro / Micro / Per-class metrics (Test set)

- Macro Precision: 0.2165

- Macro Recall:    0.2371

- Macro F1:        0.1853

- Micro Precision: 0.2108

- Micro Recall:    0.2108

- Micro F1:        0.2108


## Top / Bottom classes by AUC (Test set)

### Top 5 classes by AUC

- car_side (class 16): AUC = 1.0000

- leopards (class 57): AUC = 0.9992

- inline_skate (class 51): AUC = 0.9988

- airplanes (class 1): AUC = 0.9956

- schooner (class 80): AUC = 0.9955


### Bottom 5 classes by AUC

- elephant (class 33): AUC = 0.5567

- ant (class 3): AUC = 0.5357

- cannon (class 15): AUC = 0.4785

- cougar_body (class 21): AUC = 0.4648

- water_lilly (class 96): AUC = 0.4389


## Files saved

- `classification_report.txt` (detailed per-class precision/recall/f1)

- `per_class_metrics.csv` (precision, recall, f1, support per class)

- `test_predictions.csv` (one row per test example: true/pred/probs)

- `confusion_matrix.png`

- `roc_multiclass.png`

- `sample_predictions_grid.png`

- `sample_visuals/` (individual sample images)

- Training history plots: `accuracy_stage1.png`, `loss_stage1.png`, `accuracy_stage2.png`, `loss_stage2.png`


## Quick analysis notes

- چون مدل پایه روی CIFAR-10 آموزش دیده، قبل از فاین‌تیون دقت شانس‌محور بود.

- انجام دو فاز آموزش (فقط لایه آخر سپس فاین‌تیون کل مدل) باعث بهبود نسبی شد؛ با نگاه به نمودارهای آموزش می‌توانید over/under-fitting را بررسی کنید.

- AUC های برخی کلاس‌ها بالا و برخی بسیار پایین‌اند — دلایل محتمل: تعداد نمونه‌های کم در آن کلاس‌ها، شباهت ظاهری بین چند کلاس، یا پراکندگی زیاد تصاویر آن کلاس.

- پیشنهادات: افزایش data augmentation، افزایش اندازه تصویر (مثلاً 64x64 یا 128x128) اگر محاسبات اجازه دهد، و استفاده از یک backbone قوی‌تر (مثلاً MobileNet/VGG/ResNet pretrained) به جای شبکهٔ کوچک CIFAR-10.
