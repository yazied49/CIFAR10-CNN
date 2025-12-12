# CIFAR-10 CNN Classifier

This repository contains a Convolutional Neural Network (CNN) model implemented in TensorFlow/Keras to classify images from the **CIFAR-10 dataset**. The model is trained with data augmentation and optimized using early stopping, learning rate reduction, and checkpointing for best validation accuracy.

---

## 📁 Repository Contents

- `CIFAR10_CNN_Notebook.ipynb` – Jupyter Notebook containing:
  - Data loading and preprocessing
  - Data augmentation
  - Model architecture definition
  - Training and evaluation
  - Accuracy and loss visualization
- `best_model.keras` – The trained CNN model saved with the best validation accuracy.

---

## 🛠 Project Details

### Dataset
- **CIFAR-10**: 60,000 32x32 color images in 10 classes, with 50,000 training images and 10,000 test images.
- Classes: `airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck`

### Preprocessing
- Normalization: pixel values scaled to [0, 1].
- Labels converted to one-hot encoding.
- Train-validation split: 80%-20%.

### Data Augmentation
Applied to training set using `ImageDataGenerator`:
- Rotation, width & height shift
- Shear and zoom
- Horizontal flip

### CNN Architecture
- 3 convolutional blocks with Conv2D → BatchNorm → Conv2D → MaxPooling
- GlobalAveragePooling2D instead of Flatten
- Dense layer with 512 units + Dropout
- Output Dense layer with 10 units (softmax)

### Callbacks
- **EarlyStopping**: Stops training if validation accuracy does not improve for 10 epochs.
- **ReduceLROnPlateau**: Reduces learning rate when validation loss plateaus.
- **ModelCheckpoint**: Saves the best model by validation accuracy.

---

## 📈 Results

- Final validation accuracy: **~86.6%**
- Final test accuracy: **~85–86%**
- Training and validation curves are plotted for visualization of accuracy and loss over epochs.
