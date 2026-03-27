# Transfer Learning with Pre-trained CNNs

**MLNN Tutorial — University of Hertfordshire — 2025**

Reusing 1.2 Million Images Without Downloading Them.

---

## What This Tutorial Covers

This repository contains a complete tutorial on transfer learning using ImageNet pre-trained CNNs applied to CIFAR-10. It demonstrates that a ResNet-50 fine-tuned on just 500 images achieves higher accuracy than the same network trained from scratch on 5,000 images — ten times less data for better performance.

**Topics covered:**

- Why transfer learning works — filter universality and Centred Kernel Alignment (CKA)
- Three transfer learning strategies: feature extraction, partial fine-tuning, full fine-tuning
- Experiments across dataset sizes (50–5,000 images) and four architectures
- Discriminative learning rates (Howard & Ruder, 2018)
- Negative transfer — when it fails and how to diagnose it
- Practical fine-tuning checklist

---

## Repository Contents

```
transfer-learning-tutorial/
├── transfer_learning_tutorial.ipynb   # Main Jupyter notebook — run this
├── transfer_learning_tutorial.pdf     # Tutorial document (PDF submission)
├── transfer_learning_tutorial.docx    # Tutorial document (Word format)
├── README.md                          # This file
├── LICENSE                            # MIT licence
└── figures/                           # Generated figures (created by notebook)
    ├── fig1_training_curves.png
    ├── fig2_accuracy_vs_size.png
    ├── fig3_model_comparison.png
    ├── fig4_confusion_matrix.png
    └── fig5_cka_similarity.png
```

---

## How to Run

### 1. Install requirements

```bash
pip install torch torchvision numpy matplotlib scikit-learn jupyter
```

GPU is recommended but not required — the notebook runs on CPU with smaller subsets.

### 2. Launch the notebook

```bash
jupyter notebook transfer_learning_tutorial.ipynb
```

### 3. Run all cells

Select **Kernel → Restart & Run All**.

CIFAR-10 (~170 MB) will download automatically on first run and cache to `./data/`.

---

## Key Results

| Method | Accuracy (500 images) |
|--------|----------------------|
| From scratch (ResNet-50) | ~38% |
| Feature extraction (ResNet-50) | ~72% |
| Partial fine-tuning (ResNet-50) | ~76% |
| Discriminative fine-tuning | ~78% |

All four architectures tested (AlexNet, VGG-16, ResNet-50, EfficientNet-B0) show large gains from transfer learning.

---

## Accessibility

All figures in this tutorial are designed to be accessible:

- **Colourblind-safe palette** — Okabe-Ito (2002) throughout
- **Hatch patterns + colour** — bar charts never use colour as the sole encoding
- **Distinct markers** — line plots use circle, square, and triangle markers
- **Viridis colourmap** — perceptually uniform, greyscale-safe (confusion matrix)
- **Alt text** — all figures include descriptive alt-text in the tutorial document
- **Structured headings** — H1/H2 hierarchy supports screen readers
- **Code comments** — every non-trivial step explained inline

---

## References

1. He, K., Zhang, X., Ren, S. and Sun, J. (2016) 'Deep residual learning for image recognition', *CVPR 2016*. https://arxiv.org/abs/1512.03385
2. Howard, J. and Ruder, S. (2018) 'Universal Language Model Fine-tuning for Text Classification', *ACL 2018*. https://arxiv.org/abs/1801.06146
3. Kornblith, S., Norouzi, M., Lee, H. and Hinton, G. (2019) 'Similarity of Neural Network Representations Revisited', *ICML 2019*. https://arxiv.org/abs/1905.00414
4. Krizhevsky, A. (2009) *Learning Multiple Layers of Features from Tiny Images*. https://www.cs.toronto.edu/~kriz/cifar.html
5. Okabe, M. and Ito, K. (2002) *Color Universal Design*. https://jfly.uni-koeln.de/color/
6. Pan, S.J. and Yang, Q. (2010) 'A survey on transfer learning', *IEEE TKDE*, 22(10), pp. 1345–1359.
7. Raghu, M., Unterthiner, T., Kornblith, S., Zhang, C. and Dosovitskiy, A. (2021) 'Do Vision Transformers See Like CNNs?', *NeurIPS 34*. https://arxiv.org/abs/2108.08810
8. Tan, M. and Le, Q.V. (2019) 'EfficientNet: Rethinking model scaling', *ICML 2019*. https://arxiv.org/abs/1905.11946
9. Yosinski, J., Clune, J., Bengio, Y. and Lipson, H. (2014) 'How transferable are features in deep neural networks?', *NeurIPS 27*. https://arxiv.org/abs/1411.1792
10. Zeiler, M.D. and Fergus, R. (2014) 'Visualizing and understanding convolutional networks', *ECCV 2014*. https://arxiv.org/abs/1311.1901

---

## Licence

MIT — see [LICENSE](LICENSE). You are free to use, modify, and distribute this code with attribution.

---

## Author

University of Hertfordshire — MLNN Assignment — 2025
