
# Apple Tree Disease Classification Using CNN

## 1. Project Overview

This project uses Convolutional Neural Networks (CNNs) and image classification techniques to identify diseases in apple tree leaves.

The model classifies apple leaf images into four categories:

- Healthy
- Multiple Diseases
- Rust
- Scab

The objective is to assist in identifying apple leaf diseases using deep learning and image processing techniques.

---

## 2. Problem Statement

Apple trees can be affected by various diseases that impact plant health and crop production. Manual identification of these diseases can be time-consuming and requires specialized knowledge.

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

The project uses the **Plant Pathology 2020 FGVC7 dataset**.

Dataset link:

[Plant Pathology 2020 FGVC7 Dataset](https://www.kaggle.com/competitions/plant-pathology-2020-fgvc7/overview)

The dataset contains images of apple leaves belonging to the following categories:

- Healthy
- Multiple Diseases
- Rust
- Scab

The training data includes image identifiers and corresponding class labels.

### Dataset Structure

The dataset should be downloaded separately and placed in the appropriate project directories.

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

**Note:** The dataset is not included in the repository and must be downloaded separately.

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
- tqdm
- natsort

---

## 6. Environment Setup

### Step 1: Clone the Repository

```bash
git clone https://github.com/ishaan24bai10150/cvproject.git
cd cvproject
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

If a `requirements.txt` file is available, install the dependencies using:

```bash
pip install -r requirements.txt
```

### Step 5: Install the Jupyter Kernel

```bash
python -m ipykernel install --user --name apple-tree-disease-env
```

---

## 7. Configuration

The notebook may contain local file paths. These paths should be updated according to the location of the project on the user's computer.

A recommended path configuration is:

```python
from pathlib import Path

PROJECT_DIR = Path.cwd()

IMAGE_DIR = PROJECT_DIR / "images"
TRAIN_CSV = PROJECT_DIR / "train.csv"
TEST_CSV = PROJECT_DIR / "test.csv"
```

Before running the project, verify that:

- The dataset has been downloaded.
- The image directory exists.
- The CSV files are available.
- The image names match the dataset labels.
- The required folders have the correct paths.
- No personal or system-specific file paths are used.

---

## 8. Running the Project

The project is primarily implemented using Jupyter Notebook.

### Step 1: Start Jupyter Notebook

Run the following command from the project directory:

```bash
jupyter notebook
```

Alternatively, launch Jupyter using:

```bash
python -m notebook
```

### Step 2: Open the Project Notebook

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

**Note:** The current implementation is notebook-based. The complete workflow is performed through the notebook rather than a separate command-line Python entry-point script.

---

## 9. Image Preprocessing

The project performs the following preprocessing operations:

- Reads image files.
- Resizes images to 256 × 256 pixels.
- Converts images into numerical arrays.
- Normalizes pixel values.
- Organizes images into class-specific folders.
- Applies image augmentation.
- Divides the image data into training and validation subsets.

### Image Augmentation

The implementation uses the following image augmentation techniques:

- Rescaling
- Shearing
- Zooming
- Horizontal flipping
- Vertical flipping

These operations help the model learn visual patterns from different variations of input images.

The image generator uses a validation split of 20%.

---

## 10. CNN Architecture

The classification model is built using the Keras Sequential API.

The architecture includes:

1. Convolutional layers.
2. Max-pooling layers.
3. Flatten layer.
4. Fully connected dense layer.
5. Softmax output layer.

The model classifies images into four categories:

```python
categories = [
    "healthy",
    "multiple_diseases",
    "rust",
    "scab"
]
```

### Input Configuration

- Input image size: 256 × 256 pixels
- Number of input channels: 3
- Output classes: 4

### Model Configuration

- Optimizer: Adam
- Loss function: Categorical Crossentropy
- Evaluation metric: Accuracy
- Maximum epochs: 30
- Early stopping: Used where configured
- Model checkpointing: Used where configured

---

## 11. Model Training

During training, the CNN learns visual patterns associated with different apple leaf conditions.

The model is trained using the prepared training dataset, while validation data is used to monitor performance during training.

The following metrics can be monitored:

- Training accuracy
- Validation accuracy
- Training loss
- Validation loss

The project uses model checkpointing to save the trained model and early stopping where configured.

The model is saved using the following filenames in the implementation:

```text
apple_tree_diseases.h5
Apple_Tree_Disease.h5
```

---

## 12. Prediction Process

The prediction process consists of the following steps:

1. Load a trained model.
2. Load an input image.
3. Resize the image to 256 × 256 pixels.
4. Convert the image into an array.
5. Normalize the pixel values.
6. Add a batch dimension.
7. Pass the image through the trained CNN model.
8. Identify the class with the highest predicted probability.
9. Display the predicted disease category.

The prediction output should be considered an assistance tool and not a replacement for professional agricultural diagnosis.

---

## 13. Recommended Project Structure

The repository should contain the files required to run and understand the project.

A recommended structure is:

```text
project-root/
├── images/
├── train.csv
├── test.csv
├── project.ipynb
├── models/
│   └── apple_tree_diseases.h5
├── outputs/
│   ├── accuracy_plot.png
│   └── loss_plot.png
├── requirements.txt
├── README.md
└── .gitignore
```

**Note:** The exact structure should match the files available in the repository. Files and folders should only be listed if they are included in the project.

---

## 14. Reproducibility Checklist

Before running the project, verify the following:

- [ ] Python is installed.
- [ ] A virtual environment is created.
- [ ] Required dependencies are installed.
- [ ] The dataset is downloaded.
- [ ] Dataset paths are configured.
- [ ] The notebook opens successfully.
- [ ] Image preprocessing works correctly.
- [ ] The model trains successfully.
- [ ] Training and validation metrics are generated.
- [ ] Accuracy and loss plots are generated.
- [ ] The trained model is saved.
- [ ] Prediction works on a sample image.
- [ ] No private credentials or personal file paths are uploaded.
- [ ] External sources and reused code are acknowledged.

---

## 15. Limitations

- Model performance depends on the quality and distribution of the dataset.
- The model may not generalize to all lighting conditions, backgrounds, and camera angles.
- Local file paths may require modification on different systems.
- The current implementation is primarily notebook-based.
- Predictions may be inaccurate for images that differ significantly from the training dataset.
- The model does not replace professional plant disease diagnosis.
- The model's performance should be evaluated further before real-world agricultural deployment.

---

## 16. References

1. **Plant Pathology 2020 FGVC7 Dataset**

   https://www.kaggle.com/competitions/plant-pathology-2020-fgvc7/overview

2. **TensorFlow Documentation**

   https://www.tensorflow.org/

3. **Keras Documentation**

   https://keras.io/

---

## 17. License and Attribution

The dataset, external libraries, and any reused implementation must be used according to their respective licenses and usage conditions.

External sources and reused code should be acknowledged appropriately.

All modifications, experiments, and reported results should be documented accurately. The project is intended for educational and research purposes.
