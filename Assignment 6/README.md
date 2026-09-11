# Assignment 6 - CNN for Tomato Disease Classification

## Aim

To design and implement a Convolutional Neural Network (CNN) for
image classification using a tomato leaf disease dataset.

## Dataset

The dataset contains images of tomato leaves belonging to 10 classes.

### Classes

1. Tomato___Bacterial_spot
2. Tomato___Early_blight
3. Tomato___Late_blight
4. Tomato___Leaf_Mold
5. Tomato___Septoria_leaf_spot
6. Tomato___Spider_mites Two-spotted_spider_mite
7. Tomato___Target_Spot
8. Tomato___Tomato_Yellow_Leaf_Curl_Virus
9. Tomato___Tomato_mosaic_virus
10. Tomato___healthy

### Dataset Size

- Training images: 10,000
- Validation images: 1,000
- Number of classes: 10
- Images per training class: 1,000
- Images per validation class: 100

## Technologies Used

- Python
- TensorFlow
- Keras
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- Jupyter Notebook

## CNN Architecture

The CNN consists of:

- Data Augmentation
- Rescaling
- Conv2D - 32 filters
- MaxPooling2D
- Conv2D - 64 filters
- MaxPooling2D
- Conv2D - 128 filters
- MaxPooling2D
- Flatten
- Dense - 128 neurons
- Dropout - 0.5
- Dense - 10 neurons
- Softmax output

## Data Augmentation

The following augmentation techniques were used:

- Horizontal flipping
- Random rotation
- Random zoom

These techniques help improve model generalization.

## Training

The model was trained using:

- Optimizer: Adam
- Loss function: Sparse Categorical Crossentropy
- Batch size: 32
- Epochs: 10
- Input image size: 128 × 128 × 3

## Evaluation Metrics

The CNN was evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- Classification Report
- Confusion Matrix

## Results

The final model performance is reported in the notebook using
validation accuracy, precision, recall, and F1-score.

Training and validation accuracy and loss graphs were also generated.

## Conclusion

The CNN successfully performs classification of tomato leaf images
into different disease categories. The model can identify visual
patterns associated with tomato diseases and can potentially assist
in early disease detection.

## Files

- Assignment_6_CNN_Tomato_Disease.ipynb
- README.md
- accuracy_graph.png
- loss_graph.png
- tomato_disease_cnn.keras