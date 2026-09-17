
# Apple Tree Disease Classification Using CNN

## 1. Project Overview

This project uses Convolutional Neural Networks (CNNs) and image classification techniques to identify diseases in apple tree leaves.

The model classifies input images into four categories:

- Healthy
- Multiple Diseases
- Rust
- Scab

The objective is to assist in identifying apple leaf diseases using deep learning and image processing.

---

## 2. Problem Statement

Apple trees can be affected by various diseases that impact plant health and crop production. Manual identification of these diseases can be time-consuming and requires expertise.

This project aims to develop an image classification model that identifies whether an apple leaf is healthy or affected by rust, scab, or multiple diseases.

---

## 3. Objectives

- Classify apple leaf images into four categories.
- Preprocess and resize images for deep learning.
- Apply image augmentation to improve model generalization.
- Train a CNN-based image classification model.
- Evaluate model performance using training and validation data.
- Predict the disease category of a new input image.

---

## 4. Dataset

The project uses the Plant Pathology 2020 FGVC7 dataset.

Dataset link:

https://www.kaggle.com/competitions/plant-pathology-2020-fgvc7/overview

The dataset contains images of apple leaves with the following categories:

- Healthy
- Multiple Diseases
- Rust
- Scab

The training data includes image identifiers and corresponding class labels.

### Dataset Structure

```text
project-root/
├── images/
│   ├── Train_0.jpg
│   ├── Train_1.jpg
│   └── ...
├── train.csv
├── test.csv
├── project.ipynb
└── README.md
```

The dataset should be downloaded separately and placed in the appropriate directories.

---

## 5. Technologies Used

- Python
- TensorFlow
- Keras
- NumPy
- Pandas
- OpenCV
- Matplotlib
- Pillow
- Scikit-learn
- Jupyter Notebook

---

## 6. Environment Setup

### Step 1: Clone the Repository

```bash
git clone https://github.com/<your-username>/<your-repository>.git
cd <your-repository>
```

### Step 2: Create a Virtual Environment

#### Windows

```powershell
python -m venv .venv
.venv\Scripts\activate
```

#### Linux/macOS

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### Step 3: Upgrade pip

```bash
python -m pip install --upgrade pip
```

### Step 4: Install Dependencies

```bash
pip install numpy pandas opencv-python pillow matplotlib tqdm natsort scikit-learn tensorflow jupyter
```

If a `requirements.txt` file is available:

```bash
pip install -r requirements.txt
```

### Step 5: Install Jupyter Kernel

```bash
python -m ipykernel install --user --name apple-tree-disease-env
```

---

## 7. Configuration

The notebook may contain local file paths. These paths must be updated according to the location of the project on the user's computer.

Recommended configuration:

```python
from pathlib import Path

PROJECT_DIR = Path.cwd()
IMAGE_DIR = PROJECT_DIR / "images"
TRAIN_CSV = PROJECT_DIR / "train.csv"
TEST_CSV = PROJECT_DIR / "test.csv"
```

Before running the project, verify that:

- The dataset is downloaded.
- The image directory exists.
- The CSV files are available.
- The image names match the dataset labels.
- The required folders have the correct paths.

---

## 8. Running the Project

### Using Jupyter Notebook

Start Jupyter Notebook from the project directory:

```bash
jupyter notebook
```

Open the project notebook and execute the cells in the following order:

1. Import the required libraries.
2. Load the dataset.
3. Inspect the image labels.
4. Prepare the image directories.
5. Organize images into their respective classes.
6. Preprocess the images.
7. Configure image augmentation.
8. Build the CNN model.
9. Compile the model.
10. Train the model.
11. Evaluate training and validation performance.
12. Save the trained model.
13. Run predictions on sample images.

### Command-Line Launch

```bash
python -m notebook
```

> The current implementation is primarily notebook-based. A separate Python entry-point script should be added if the evaluator requires direct script-based execution.

---

## 9. Image Preprocessing

The project performs the following preprocessing operations:

- Reads image files.
- Resizes images to 256 × 256 pixels.
- Converts images into numerical arrays.
- Normalizes pixel values.
- Organizes images into class-specific folders.
- Applies image augmentation.

The image data is divided into training and validation subsets.

### Image Augmentation

The implementation uses techniques such as:

- Rescaling
- Shearing
- Zooming
- Horizontal flipping
- Vertical flipping

These operations help the model learn from variations in the input images.

---

## 10. CNN Architecture

The classification model is built using the Keras Sequential API.

The architecture includes:

1. Convolutional layers.
2. Max-pooling layers.
3. Flatten layer.
4. Fully connected dense layer.
5. Softmax output layer.

The output layer contains four classes:

```python
categories = [
    "healthy",
    "multiple_diseases",
    "rust",
    "scab"
]
```

### Model Configuration

- Optimizer: Adam
- Loss Function: Categorical Crossentropy
- Evaluation Metric: Accuracy
- Maximum Epochs: 30
- Early Stopping: Used where configured
- Model Checkpointing: Used where configured

---

## 11. Model Training

During training, the model learns patterns associated with different apple leaf conditions.

Training and validation metrics are monitored to identify model performance and potential overfitting.

The following outputs may be generated:

- Training accuracy
- Validation accuracy
- Training loss
- Validation loss
- Saved trained model

---

## 12. Prediction Process

The prediction process consists of the following steps:

1. Load an input image.
2. Resize the image to the required dimensions.
3. Convert the image into an array.
4. Normalize the pixel values.
5. Add a batch dimension.
6. Pass the image through the trained model.
7. Identify the class with the highest predicted probability.
8. Display the predicted category.

The model's output should be considered an assistance tool and not a replacement for professional agricultural diagnosis.

---

## 13. Recommended Project Structure

```text
project-root/
├── data/
│   └── README.md
├── notebooks/
│   └── apple_tree_disease_classification.ipynb
├── models/
│   └── apple_tree_diseases.h5
├── outputs/
│   ├── accuracy_plot.png
│   └── loss_plot.png
├── requirements.txt
├── README.md
└── .gitignore
```

The exact structure should match the files included in the repository.

---

## 14. Reproducibility Checklist

- [ ] Python is installed.
- [ ] A virtual environment is created.
- [ ] Required dependencies are installed.
- [ ] The dataset is downloaded.
- [ ] Dataset paths are configured.
- [ ] The notebook runs without errors.
- [ ] Image preprocessing works correctly.
- [ ] The model trains successfully.
- [ ] Accuracy and loss plots are generated.
- [ ] The trained model is saved.
- [ ] Prediction works on a sample image.
- [ ] No private credentials or personal file paths are uploaded.
- [ ] External sources and reused code are acknowledged.

---

## 15. Limitations

- Model performance depends on dataset quality.
- The model may not generalize to all lighting conditions and camera angles.
- Hard-coded paths may require modification on different systems.
- The current implementation is primarily notebook-based.
- Predictions may be inaccurate for images that differ from the training dataset.
- The model does not replace professional plant disease diagnosis.

---

## 16. References

1. Plant Pathology 2020 FGVC7 Dataset:

   https://www.kaggle.com/competitions/plant-pathology-2020-fgvc7/overview

2. TensorFlow Documentation:

   https://www.tensorflow.org/

3. Keras Documentation:

   https://keras.io/

---

## 17. License and Attribution

The dataset, external libraries, and any reused implementation must be used according to their respective licenses and usage conditions.

External sources and reused code should be acknowledged appropriately. Any modifications, experiments, and reported results should be documented accurately.
