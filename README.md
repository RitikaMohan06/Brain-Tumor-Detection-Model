#  Brain Tumor Classification Using CNN

A Deep Learning project that classifies Brain MRI images into different tumor categories using a Convolutional Neural Network (CNN) built with TensorFlow and Keras.

##  Overview

Brain tumors can be life-threatening if not detected early. This project uses Computer Vision and Deep Learning techniques to automatically classify MRI brain scans into one of four categories:

- Glioma Tumor
- Meningioma Tumor
- Pituitary Tumor
- No Tumor

The model is trained on MRI images and learns meaningful patterns to distinguish between different tumor types.

---

##  Features

- MRI Image Classification

- Deep Learning-based CNN Model

- Data Preprocessing and Normalization

- Training and Validation Performance Visualization

- Model Saving for Future Predictions

---

##  Tech Stack

- Python
- TensorFlow
- Keras
- OpenCV
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- Kaggle Notebook

---

##  Dataset

The dataset contains MRI brain scans categorized into four classes:

| Label | Description |
|---------|-------------|
| Glioma | Tumor originating from glial cells |
| Meningioma | Tumor arising from the meninges |
| Pituitary | Tumor located in the pituitary gland |
| No Tumor | Healthy MRI scan |

---

##  Model Architecture

The CNN model consists of:

```text
Input Layer (150 × 150 × 3)

↓
Conv2D + ReLU

↓
Conv2D + ReLU

↓
MaxPooling2D

↓
Dropout

↓
Conv2D + ReLU

↓
Conv2D + ReLU

↓
MaxPooling2D

↓
Dropout

↓
Flatten

↓
Dense Layer

↓
Output Layer (Softmax)
```

---

##  Data Preprocessing

The following preprocessing steps were performed:

- Image resizing to 150 × 150 pixels
- Image normalization
- Label encoding
- Train/Test split
- Data shuffling

---

##  Training Configuration

```python
Optimizer = Adam
Loss Function = Categorical Crossentropy
Metrics = Accuracy
Epochs = 20
```

---

##  Results

The model was evaluated using:

- Training Accuracy
- Validation Accuracy
- Training Loss
- Validation Loss

The learning curves demonstrate effective training and good generalization performance.

---

##  Model Saving

The trained model is saved as:

```python
braintumor.h5
```

Load the model using:

```python
from tensorflow.keras.models import load_model

model = load_model("braintumor.h5")
```

---

##  Making Predictions

```python
img = cv2.imread("image.jpg")
img = cv2.resize(img, (150,150))

img = np.array(img)
img = img.reshape(1,150,150,3)

prediction = model.predict(img)
```

Class Labels:

```python
[
    "glioma_tumor",
    "meningioma_tumor",
    "no_tumor",
    "pituitary_tumor"
]
```

---

##  Project Structure

```text
Brain-Tumor-Classification/
│
├── brain-tumor.ipynb
├── braintumor.h5
├── README.md
│
└── Dataset/
    ├── Training/
    └── Testing/
```

---

##  Future Improvements

- Transfer Learning (ResNet50, EfficientNet, VGG16)
- Data Augmentation
- Hyperparameter Tuning
- Streamlit Web App Deployment
- Grad-CAM Visualization
- Model Explainability

---

##  Author

**Ritika Mohan**

