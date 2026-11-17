# Crop Growth Health Phenotypic Prediction Model

This image-based model assesses crop health by predicting disease, pest, and growth-status labels from visible plant phenotypes. A single ConvNeXt-Tiny network produces 111 outputs across the three tasks.

## Model download

[Download the model from Google Drive](https://drive.google.com/drive/folders/12abHI-iPnksB-RsNHzff1hVS0iZ5h4-N?usp=drive_link)

## Model and data

| Item | Details |
| --- | --- |
| Backbone | ConvNeXt-Tiny |
| Model parameters | Approximately 27.91 million |
| Output labels | 50 disease, 49 pest, and 12 growth-status labels |
| Training image records | 81,312 |
| Validation image records | 17,356 |
| Total image records | 98,668 |

## Validation results

| Evaluation group | Image records | Macro-precision | Macro-recall | Macro-F1 |
| --- | ---: | ---: | ---: | ---: |
| Overall disease and pest evaluation | 17,356 | 87.80% | 90.32% | 88.16% |
| Tomato | 6,034 | 81.61% | 90.05% | 84.94% |
| Lettuce | 712 | 80.91% | 78.04% | 78.25% |

The reported overall macro-average precision (Macro-AP) was **0.9245**. The lettuce evaluation covers diseases, symptoms, nutritional conditions, and health status. The validation set was used for model selection and threshold calibration. Independent test-set performance has yet to be evaluated.

## Inference benchmark

Inference was benchmarked with ONNX on CPU and PyTorch on an NVIDIA GeForce RTX 3080. The benchmark used FP32, a batch size of 1, 20 warm-up runs, and 100 timed runs per setup. Timing excludes image preprocessing, model loading, and the full agent workflow. CPU and GPU measurements used different inference engines.
