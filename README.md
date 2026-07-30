# TCM-93class-decoction-benchmark

Split indices, class-label mapping, trained model weights, and analysis code for a **93-class Traditional Chinese Medicine (TCM) decoction-piece image-classification benchmark**.

This repository accompanies the manuscript *"Image-Based Sensing and Deep Learning for Quality Control of Traditional Chinese Medicine Decoction Pieces: A 93-Class Benchmark Study."* It is released to make all reported results fully reproducible.

---

## What this repository contains

| Item | File / location |
|---|---|
| Class-label mapping (index → herb name) | `manifests_out/class_labels.json` |
| Training split (fixed, seed = 42) | `manifests_out/train_split.csv` |
| Validation split | `manifests_out/val_split.csv` |
| Independent test split | `manifests_out/test_split.csv` |
| Training / evaluation code | `main script20.ipynb` |
| Trained model weights | see **Releases** |

The dataset used in the paper contains **9,285 images across 93 categories**, split into training (6,767), validation (751), and independent test (1,767) sets.

---

## Important note on the images (data availability & copyright)

**This repository does NOT contain, and does NOT redistribute, the original herb images.**

The original photographs were **not captured by the author** and were compiled and circulated by a third party **without an explicit open license**. To respect the original authors' rights, only the following are released here: the class-label mapping, the fixed train/validation/test split indices, the analysis code, and the trained model weights. These artifacts are sufficient to reproduce every result reported in the manuscript on the identical data split.

Researchers who wish to obtain the raw images can source them from publicly available TCM decoction-piece image collections and align them to the released split indices via the file names in the split CSVs.

---

## Licensing

- **Code and split/label files** in this repository are released under the **MIT License** (see `LICENSE`).
- **The MIT License applies only to the material authored by the repository owner.** It does **not** grant any rights to the original herb images, whose copyright remains with their respective owners. No image data is distributed here.

---

## How to reproduce the results

1. Obtain the raw TCM decoction-piece images from a publicly available collection.
2. Organize them according to the file names listed in `manifests_out/train_split.csv`, `val_split.csv`, and `test_split.csv` (the split is fixed with random seed 42).
3. Map class indices to herb names using `manifests_out/class_labels.json`.
4. Run `main script20.ipynb` to train/evaluate, or load the released weights (see **Releases**) to reproduce the reported test-set metrics directly.

Reported environment: Python, PyTorch / torchvision, single NVIDIA Tesla T4 GPU (Google Colab). Training protocol: Adam, learning rate 1e-4, 20 epochs, 224×224 input.

---

## Citation

**Author:** Zigang Shao — ORCID: [0009-0008-9105-1861](https://orcid.org/0009-0008-9105-1861)

If you use this benchmark, please cite the associated article (full citation will be added once the paper is published). For now, please reference this repository:

```
Zigang Shao (ORCID: 0009-0008-9105-1861).
TCM-93class-decoction-benchmark.
https://github.com/shaozigang/TCM-93class-decoction-benchmark
```
