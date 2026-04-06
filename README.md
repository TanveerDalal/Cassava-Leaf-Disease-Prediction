# Cassava Leaf Disease Classification 🌿

## 📌 Project Overview

This project focuses on **automated classification of cassava leaf diseases** using deep learning techniques. Cassava is a critical food crop in Africa, and early detection of diseases can significantly improve crop yield and food security.

The goal is to classify images of cassava leaves into **5 categories**:

* Cassava Bacterial Blight (CBB)
* Cassava Brown Streak Disease (CBSD)
* Cassava Green Mottle (CGM)
* Cassava Mosaic Disease (CMD)
* Healthy

---

## 🎯 Objectives

* Build a **baseline custom CNN model**
* Apply **transfer learning using pretrained models**
* Perform **fine-tuning for performance improvement**
* Experiment with different architectures and justify model choices
* Evaluate models using accuracy, loss, and confusion matrices

---

## 📊 Dataset

* Total images: ~21,000+
* Source: Kaggle Cassava Leaf Disease Classification
* Images collected from real farms in Uganda
* Real-world challenges:

  * varying lighting conditions
  * different camera qualities
  * class imbalance

---

## ⚙️ Methodology

### 1. Data Preparation

* Train-validation split (80/20)
* Image resizing and normalization
* Data augmentation (for robustness)

---

### 2. Custom CNN Models

Three CNN architectures were tested:

| Model | Description          |
| ----- | -------------------- |
| CNN-2 | 2 convolution blocks |
| CNN-3 | 3 convolution blocks |
| CNN-4 | 4 convolution blocks |

#### Result:

* Performance improved with depth
* Best custom CNN: **CNN-4 (~76% validation accuracy)**
* Diminishing returns observed with increasing depth

---

### 3. Transfer Learning (Feature Extraction)

Pretrained models used:

* ResNet18
* ResNet34
* EfficientNet-B0

#### Key Finding:

* Frozen pretrained models **underperformed (~71–72%)**
* Indicated **underfitting**
* Pretrained features alone were insufficient for this dataset

---

### 4. Fine-Tuning

EfficientNet-B0 was selected for fine-tuning:

| Strategy            | Validation Accuracy |
| ------------------- | ------------------- |
| Frozen              | ~72%                |
| Last Block Unfrozen | ~75%                |
| All Layers Unfrozen | **~84%**            |

#### Key Insight:

* Fine-tuning significantly improved performance
* Full unfreezing enabled adaptation to cassava-specific features
* Mild overfitting observed but acceptable

---

## 🏆 Final Model

**EfficientNet-B0 (Fully Fine-Tuned)**

* Validation Accuracy: **~84%**
* Best overall performance
* Successfully balances feature learning and generalization

---

## 📈 Key Insights

* Increasing CNN depth improves performance but with diminishing returns
* Transfer learning without fine-tuning leads to underfitting
* Domain-specific adaptation is critical for plant disease detection
* Fine-tuning pretrained models provides the best results

---

## 🧪 Evaluation Metrics

* Training Accuracy
* Validation Accuracy
* Loss Curves
* Confusion Matrix

---

## 💻 Environment

* Platform: Kaggle Notebook
* GPU: T4 GPU
* Framework: PyTorch
* Libraries:

  * torchvision
  * numpy
  * pandas
  * matplotlib
  * seaborn

---

## 🚀 How to Run

1. Open the notebook in Kaggle
2. Attach dataset:

   ```
   cassava-leaf-disease-classification
   ```
3. Run all cells sequentially

---

## 📌 Future Improvements

* Hyperparameter tuning
* Learning rate scheduling
* Advanced augmentation techniques
* Ensemble models
* Deployment on mobile devices

---

## 📜 Conclusion

This project demonstrates that:

> Fine-tuning pretrained models is essential for achieving high performance in domain-specific image classification tasks.

EfficientNet-B0 with full fine-tuning achieved the best results, making it the most suitable model for cassava disease detection.

---

## 👨‍💻 Author

* Tanveer Dalal

---

## ⭐ If you found this useful

Consider giving this repo a star ⭐