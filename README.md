# Plant Disease Classification with TensorFlow

This project aims to classify potato plant images into three classes (Early Blight, Late Blight, Healthy) using a Convolutional Neural Network (CNN) with TensorFlow and Keras.

## Prerequisites

- Python 3.x
- TensorFlow
- SciPy
- Matplotlib



## Project Structure

1. **Image Preprocessing**: Loads images from the `PlantVillage` directory, resizes and scales them.
2. **Data Augmentation**: Randomly flips and rotates images to enhance model robustness.
3. **Model Architecture**: CNN with multiple Conv2D and MaxPooling layers, followed by dense layers for classification.
4. **Training & Evaluation**: Model is trained for 50 epochs with training, validation, and test sets.

## Dataset Preparation

The dataset is structured as follows:

- Directory: `PlantVillage`
- Classes: `Potato___Early_blight`, `Potato___Late_blight`, `Potato___healthy`

### Loading Dataset

The dataset is loaded using `tf.keras.preprocessing.image_dataset_from_directory`, which:
- Shuffles the dataset.
- Resizes images to 256x256 pixels.
- Batches them for efficient training.

```python
dataset = tf.keras.preprocessing.image_dataset_from_directory(
    "PlantVillage",
    shuffle=True,
    image_size=(IMAGE_SIZE, IMAGE_SIZE),
    batch_size=BATCH_SIZE
)
