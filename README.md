---

### ✅ `README.md`

```markdown
# CIFAR-100 Image Classification 🧠📊

This project demonstrates image classification on the **CIFAR-100 dataset** using two different approaches:

1. **Custom CNN from Scratch** with:
   - Data Augmentation
   - Learning Rate Scheduler
   - Early Stopping
2. **Transfer Learning** using **ResNet-50**

---

## 📁 Project Structure

```

cifar100-classification/
├── scratch\_model.py          # CNN from scratch with DA, LR scheduler, early stop
├── resnet50\_transfer.py      # Transfer learning with ResNet-50 (optional)
├── utils.py                  # Data preprocessing and callbacks
├── requirements.txt
└── README.md

````

---

## 🧠 Dataset

**CIFAR-100** consists of 60,000 color images (32x32), 100 classes (600 images/class), with:
- 50,000 training images
- 10,000 test images

It’s automatically downloaded via `tf.keras.datasets`.

---

## 🚀 Model Training

### ✅ CNN From Scratch

Trained using:
- `Conv2D`, `MaxPooling`, `BatchNorm`, `Dropout`, `Dense`
- **Data Augmentation** (`ImageDataGenerator` or `tf.image`)
- **Learning Rate Scheduler**: `ReduceLROnPlateau`
- **Early Stopping**: Monitored validation accuracy

Run:

```bash
python scratch_model.py
````

### 🔄 Transfer Learning with ResNet-50

* Resize CIFAR-100 images to 224×224
* Use `tf.keras.applications.ResNet50`
* Fine-tune final layers or train top layers only

Run:

```bash
python resnet50_transfer.py
```

---

## 📊 Results

| Model                | Top-1 Accuracy | Top-5 Accuracy | Notes                                 |
| -------------------- | -------------- | -------------- | ------------------------------------- |
| CNN (Scratch + DA)   | **65.51%**     | **89.02%**     | With Data Augmentation, LR, EarlyStop |
| ResNet-50 (Transfer) | \~65–75%       | \~85–90%       | Coming soon                           |

### 🔍 CNN Final Output (Test Set)

```
313/313 ━━━━━━━━━━━━━━━━━━━━ 5s 16ms/step - accuracy: 0.6516 - loss: 1.2594 - top_k_categorical_accuracy: 0.8879
Test loss: 1.2397
Test accuracy: 65.51%
Test top-5 accuracy: 89.02%
```

---

## ⚙️ Features Used

* ✅ **Data Augmentation**: Random flip, crop, rotation, zoom
* ✅ **Learning Rate Scheduler**: `ReduceLROnPlateau` on val\_accuracy
* ✅ **Early Stopping**: Stops training after 5 epochs without improvement
* ✅ **Top-5 Accuracy** Metric

---

## 🧰 Requirements

```
tensorflow>=2.12.0
numpy
matplotlib
```

Install with:

```bash
pip install -r requirements.txt
```

---

## 📎 References

* [CIFAR-100 Dataset](https://www.cs.toronto.edu/~kriz/cifar.html)
* [ResNet Paper](https://arxiv.org/abs/1512.03385)

---

## 🙌 Acknowledgments

Built as part of my deep learning journey, exploring the effectiveness of both custom architectures and transfer learning techniques on real-world datasets.

---

```

Let me know if you want:
- A `requirements.txt` file auto-generated
- To export this README as a `.md` file
- Or include the exact augmentation settings you used (`rotation_range`, `zoom_range`, etc.) in the README too.
```
