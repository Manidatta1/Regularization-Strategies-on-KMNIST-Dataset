# 🧠 Regularization Strategies on KMNIST Dataset

This project explores how various regularization strategies impact the performance and generalization of a CNN-based model on the **Kuzushiji-MNIST (KMNIST)** dataset. The primary goal is to evaluate how techniques like **Dropout**, **L2 Regularization**, and **SGD with Momentum** influence classification metrics across different training data splits.

---

## 🎯 Objective

- Evaluate CNN performance on handwritten Japanese characters using KMNIST.
- Analyze how architectural choices and regularization methods affect generalization.
- Study the trade-off between data size and regularization effectiveness.

---

## 🏗️ CNN Architecture

- **Convolutional Layers**: 5 layers with filters [32, 64, 128, 256, 512], kernel size 3×3, ReLU activations.
- **Pooling**: MaxPooling used in selected layers to reduce spatial dimensions and prevent overfitting.
- **Fully Connected Layers**:
  - FC1: 512 → 512 (ReLU)
  - Output: 512 → 10 (softmax classification)
- **Regularization Variants**:
  - Dropout (p = 0.2)
  - L2 Regularization (weight decay = 0.0001)
  - SGD with Momentum (momentum = 0.9)

---

## ⚙️ Training Setup

| Hyperparameter       | Value             |
|----------------------|-------------------|
| Dataset              | KMNIST (28×28)    |
| Optimizer            | SGD               |
| Learning Rate        | 0.01              |
| Batch Size           | 64                |
| Epochs               | 5                 |
| Loss Function        | CrossEntropyLoss  |
| Hardware             | GPU/CPU           |

---

## 📊 Evaluation Metrics

- **Accuracy**
- **Precision**
- **Recall**
- **Performance comparison across data splits**: 25%, 50%, 75%, 100%

---

## 📈 Results Summary

| **Method**            | **Precision (75%)** | **Recall (75%)** | **Best Accuracy**        |
|-----------------------|---------------------|------------------|---------------------------|
| Baseline              | 0.91                | 0.90             | ~90%                      |
| Dropout (p=0.2)       | 0.90                | 0.90             | **94.65% on 25% data**    |
| L2 Regularization     | 0.90                | 0.89             | Stable but less effective |
| SGD + Momentum (0.9)  | **0.96**            | **0.96**         | **95.87% on 75% data**    |

---

## 🔍 Key Insights

- **SGD with Momentum** yields the highest overall performance but benefits most from larger datasets.
- **Dropout** improves generalization significantly even with just 25% of training data — highly data-efficient.
- **L2 Regularization** offers marginal improvements, less effective with small datasets.
- **Baseline model** suffers from overfitting without regularization.

---

## 📊 Visualizations

- Bar plots comparing accuracy, precision, and recall across techniques

---

## 🧑‍💻 Author

**Mani Datta**  
Master’s in Data Science @ University of Colorado Boulder  
[GitHub](https://github.com/Manidatta1)

---


---

## ✅ Conclusion

Regularization plays a critical role in both **improving generalization** and **reducing data dependency**. While **SGD with Momentum** delivered the **best performance** (95.87% accuracy), **Dropout** proved to be the **most efficient method**, achieving strong results with limited training data. These findings can guide the design of more robust CNNs in low-data scenarios.

---

📄 **Full Report**

For a detailed explanation of the experiment design, model architecture, hyperparameter tuning, result interpretation, and additional insights, please refer to document https://github.com/Manidatta1/Regularization-Strategies-on-KMNIST-Dataset/blob/main/Regularization%20Strategies%20on%20KMNIST%20Dataset.docx the included in this repository.


