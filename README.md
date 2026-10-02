# 🐱🐶 Dog vs Cat Classification using MobileNetV2

A computer vision project that classifies images as **Cat** or **Dog** using **Transfer Learning with MobileNetV2**.

## 📌 Project Overview

The goal of this project is to build an image classification system capable of distinguishing between cats and dogs.

Instead of training a CNN from scratch, the project uses **MobileNetV2 pretrained on ImageNet** and adds a custom classification layer for the two target classes.

### Workflow

```text
Kaggle Dataset
      ↓
Image Extraction
      ↓
Train / Validation Split
      ↓
Resize Images to 224 × 224
      ↓
MobileNetV2 Preprocessing
      ↓
Pretrained MobileNetV2
      ↓
Global Average Pooling
      ↓
Dropout
      ↓
Sigmoid Classification Layer
      ↓
Cat / Dog Prediction
```

## 📂 Dataset

The project uses the **Microsoft Cats vs Dogs** dataset obtained through Kaggle.

Dataset structure:

```text
PetImages/
├── Cat/
└── Dog/
```

After preprocessing:

```text
cat_dog_224/
├── train/
│   ├── Cat/
│   └── Dog/
│
└── validation/
    ├── Cat/
    └── Dog/
```

### Dataset Split

| Class | Training | Validation |
|---|---:|---:|
| Cat | 9,999 | 2,500 |
| Dog | 9,999 | 2,500 |
| **Total** | **19,998** | **5,000** |

Images were resized to:

```text
224 × 224 × 3
```

## 🧠 Model

The project uses **MobileNetV2** with ImageNet pretrained weights.

The pretrained convolutional layers are initially frozen and a custom classification head is added:

```text
MobileNetV2
     ↓
GlobalAveragePooling2D
     ↓
Dropout (0.2)
     ↓
Dense (1, sigmoid)
```

The final sigmoid output represents the probability of the image being a **Dog**.

```text
0 → Cat
1 → Dog
```

## ⚙️ Preprocessing

Images are:

1. Converted to RGB
2. Resized to `224 × 224`
3. Split into training and validation sets
4. Preprocessed using MobileNetV2's `preprocess_input`

MobileNetV2 preprocessing scales image pixel values appropriately for the pretrained network.

## 🛠️ Technologies Used

- Python
- TensorFlow
- Keras
- MobileNetV2
- OpenCV
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- Google Colab
- Kaggle Dataset

## 📊 Evaluation

The model can be evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix

Example:

```text
Actual → Cat
Predicted → Cat

Actual → Dog
Predicted → Dog
```

A confusion matrix can be used to analyze correct and incorrect predictions for both classes.

## 🔍 Prediction

For a new image, the image is:

```text
Input Image
    ↓
Resize to 224 × 224
    ↓
MobileNetV2 preprocessing
    ↓
Model prediction
    ↓
Cat / Dog
```

Example output:

```text
Prediction: Dog
Probability: 0.97
```

## 🚀 How to Run

### 1. Clone the repository

```bash
git clone https://github.com/mallikayush50-del/Dog-Cat-Classification-using-MobileNetV2.git
```

### 2. Open the notebook

```text
dog_vs_cat_classification.ipynb
```

The notebook can be run using:

- Google Colab
- Jupyter Notebook
- VS Code with Jupyter support

### 3. Dataset

Download the Cats vs Dogs dataset from Kaggle and update the dataset paths if necessary.

### 4. Install dependencies

```bash
pip install tensorflow numpy pandas matplotlib seaborn opencv-python pillow scikit-learn
```

## 💡 Key Learning Outcomes

Through this project, I worked with:

- Image preprocessing
- Dataset organization
- Train-validation splitting
- CNN-based image classification
- Transfer learning
- MobileNetV2
- TensorFlow/Keras
- Binary classification
- Model evaluation
- Computer vision workflows

## 🔮 Future Improvements

Possible improvements include:

- Data augmentation
- Fine-tuning the last layers of MobileNetV2
- Hyperparameter tuning
- Comparing MobileNetV2 with other pretrained CNN architectures
- Deploying the model as a web application
- Building a real-time camera-based classifier

## 👨‍💻 Author

**Ayush Mallik**

B.Tech + M.Tech Dual Degree  
Metallurgical & Materials Engineering  
NIT Rourkela

### Repository

[Dog-Cat-Classification-using-MobileNetV2](https://github.com/mallikayush50-del/Dog-Cat-Classification-using-MobileNetV2)
