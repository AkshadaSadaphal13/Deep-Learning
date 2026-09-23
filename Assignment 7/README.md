# Assignment 7 – Transfer Learning Using AlexNet, VGG16, ResNet50 and EfficientNetB0

## 1. Aim

To implement transfer learning using the pretrained CNN architectures **AlexNet, VGG16, ResNet50, and EfficientNetB0** for image classification and compare their performance based on test accuracy, number of parameters, and training time.

## 2. Introduction

Transfer learning is a deep learning technique in which a model trained on a large dataset is reused for a new, related task. Instead of training a neural network from scratch, the pretrained model provides previously learned image features that can be adapted to the target dataset.

In this assignment, four convolutional neural network (CNN) architectures pretrained on ImageNet are used for image classification on the CIFAR-10 dataset.

The experiment uses **feature-extraction transfer learning**. The pretrained backbone layers are frozen, and only the final classification layer is trained for the target dataset.

## 3. Objectives

* Understand the concept and application of transfer learning.
* Load pretrained CNN architectures using PyTorch and torchvision.
* Modify the final classifier of each model for CIFAR-10 classification.
* Freeze the pretrained layers and train only the classification head.
* Evaluate each model using test accuracy.
* Compare model size and training time.
* Visualize the comparison using bar charts.
* Identify possible improvements through further fine-tuning.

## 4. Models Used

### 4.1 AlexNet

AlexNet is a CNN architecture that uses convolutional layers followed by fully connected layers for classification. It was developed for large-scale image recognition.

In this experiment, the pretrained AlexNet model is loaded, and its final fully connected layer is replaced with a new layer containing 10 output units for CIFAR-10 classification.

### 4.2 VGG16

VGG16 is a deep CNN architecture that uses a sequence of small convolutional filters and pooling layers. It has a relatively large fully connected classifier.

The pretrained VGG16 model is used, and its final classifier layer is replaced with a 10-class output layer.

### 4.3 ResNet50

ResNet50 is a 50-layer CNN that uses residual connections. These connections help information and gradients flow through deeper networks.

For this experiment, the final fully connected layer (`fc`) is replaced with a new layer containing 10 output units.

### 4.4 EfficientNetB0

EfficientNetB0 is a CNN architecture designed to balance network depth, width, and image resolution.

Its final classifier layer is replaced with a new 10-class output layer for the CIFAR-10 dataset.

## 5. Dataset Description

### CIFAR-10

CIFAR-10 is an image classification dataset containing 10 categories of everyday objects.

The notebook uses the CIFAR-10 training and test datasets provided by `torchvision.datasets.CIFAR10`.

The dataset classes are:

1. Airplane
2. Automobile
3. Bird
4. Cat
5. Deer
6. Dog
7. Frog
8. Horse
9. Ship
10. Truck

### Dataset selection used in this experiment

| Dataset split         | Number of images used |
| --------------------- | --------------------: |
| Training subset       |                 8,000 |
| Testing subset        |                 2,000 |
| Total selected images |                10,000 |

A random subset is selected using seed `42` to make the experiment reproducible.

## 6. Tools and Technologies

* **Programming language:** Python
* **Deep learning framework:** PyTorch
* **Model library:** torchvision
* **Dataset:** CIFAR-10
* **Numerical operations:** NumPy
* **Data handling and comparison:** pandas
* **Visualization:** Matplotlib
* **Execution platform:** Google Colab
* **Suggested runtime:** GPU

## 7. Methodology

The experiment follows these steps:

1. Import the required Python libraries.
2. Set the random seed and select the available computing device.
3. Load the CIFAR-10 dataset.
4. Apply preprocessing compatible with the pretrained ImageNet weights.
5. Select 8,000 training images and 2,000 testing images.
6. Load the pretrained AlexNet, VGG16, ResNet50, and EfficientNetB0 models.
7. Replace each model's final classification layer with a 10-class layer.
8. Freeze the pretrained model parameters.
9. Unfreeze only the final classifier parameters.
10. Train the classifier for 3 epochs using the Adam optimizer.
11. Evaluate each trained model on the test subset.
12. Record test accuracy, total parameters, trainable parameters, and training time.
13. Display the comparison table and generate bar charts.
14. Discuss the observations and possible improvements.

## 8. Transfer Learning Approach

This implementation uses **feature extraction**.

The pretrained CNN backbone contains features learned from ImageNet. These layers are kept frozen, while a new classifier is trained to map the extracted features to the 10 CIFAR-10 classes.

### Layer configuration

* **Frozen layers:** All pretrained parameters are initially frozen.
* **Trainable layers:** Only the newly replaced final classifier layer is unfrozen.
* **Loss function:** Cross-Entropy Loss.
* **Optimizer:** Adam.
* **Learning rate:** `0.001`.
* **Number of epochs:** `3`.

The same training subset, testing subset, input preprocessing, batch size, optimizer, and epoch count are used across the four models to support a consistent comparison.

## 9. Implementation Details

### Preprocessing

The notebook uses preprocessing obtained from the default ResNet50 ImageNet weights:

* Crop size: `224 × 224`
* Resize size: `232`
* Training batch size: `64`
* Testing batch size: `64`

The pretrained weights' transform is applied to the CIFAR-10 images before they are passed to the models.

### Model configuration

| Model          | Final layer replaced |
| -------------- | -------------------- |
| AlexNet        | `classifier[6]`      |
| VGG16          | `classifier[6]`      |
| ResNet50       | `fc`                 |
| EfficientNetB0 | `classifier[1]`      |

Each replacement layer has 10 output units, corresponding to the 10 CIFAR-10 classes.

### Training configuration

| Parameter        | Value                                |
| ---------------- | ------------------------------------ |
| Random seed      | 42                                   |
| Batch size       | 64                                   |
| Epochs           | 3                                    |
| Optimizer        | Adam                                 |
| Learning rate    | 0.001                                |
| Loss function    | Cross-Entropy Loss                   |
| Training samples | 8,000                                |
| Testing samples  | 2,000                                |
| Device           | CUDA GPU if available, otherwise CPU |

## 10. Evaluation Metrics

The notebook records the following metrics for every model:

### Test accuracy

Test accuracy measures the proportion of test images classified correctly.

$$
\text{Accuracy}=\frac{\text{Number of correct predictions}}{\text{Total number of test images}}
$$

### Total parameters

The total number of parameters represents the number of model parameters, including frozen and trainable parameters. The notebook reports this value in millions.

### Trainable parameters

The trainable parameter count represents the parameters updated during training. In this experiment, only the final classifier is trainable.

### Training time

Training time is measured in seconds using a timer around the classifier training process.

## 11. Results and Comparison

After training and evaluation, the notebook creates a pandas DataFrame containing the following columns:

| Column                   | Description                          |
| ------------------------ | ------------------------------------ |
| `model`                  | Model architecture name              |
| `test_accuracy`          | Accuracy on the selected test subset |
| `total_parameters_m`     | Total parameters in millions         |
| `trainable_parameters_m` | Trainable parameters in millions     |
| `train_seconds`          | Training duration in seconds         |

The comparison table is sorted by test accuracy in descending order.

**Note:** The exact accuracy values, parameter counts, and training times should be taken from the output produced when the notebook is executed. They are not hard-coded in this README because they depend on the actual run.

## 12. Result Visualization

Two bar charts are generated:

1. **Accuracy comparison:** Displays the test accuracy of the four architectures.
2. **Training-time comparison:** Displays the training duration of the four architectures in seconds.

These visualizations help compare predictive performance and computational cost.

## 13. Discussion

The experiment compares four pretrained CNNs using the same feature-extraction approach.

* **AlexNet and VGG16:** Both use fully connected classification layers, and their classifier structures contribute to their parameter counts.
* **ResNet50:** Uses residual connections within its architecture.
* **EfficientNetB0:** Uses a design that balances depth, width, and image resolution.
* **Frozen backbones:** Since only the final classifier is trained, the pretrained feature-extraction layers are not updated.
* **Accuracy and computational cost:** Test accuracy, parameter counts, and training time provide different perspectives on model behaviour.

The comparison should be interpreted using the actual table and plots generated by the notebook. A higher test accuracy does not automatically mean a model has lower computational cost.

### Possible improvement

A further experiment could unfreeze the last block of the pretrained backbone and train it with a smaller learning rate, such as `1e-5`. This would be a separate fine-tuning experiment and should be compared with the original frozen-backbone results.

## 14. Conclusion

This assignment implements feature-extraction transfer learning using four ImageNet-pretrained CNN architectures: AlexNet, VGG16, ResNet50, and EfficientNetB0.

The final classifier of each model is adapted to the 10 CIFAR-10 classes, while the pretrained backbone remains frozen. The models are trained and evaluated using a consistent experimental setup, and their test accuracy, parameter counts, and training times are recorded.

The resulting table and visualizations provide a basis for discussing the differences between the architectures. The experiment can be extended by fine-tuning selected backbone layers or changing the training configuration.

## 15. How to Run the Notebook

1. Open the notebook in Google Colab or a compatible Jupyter environment.
2. If available, select a GPU runtime.
3. Run the cells from top to bottom.
4. Allow the CIFAR-10 dataset to download when prompted by the dataset loader.
5. Wait for all four models to finish training and evaluation.
6. Review the printed training accuracies, comparison table, and bar charts.
7. Use the actual outputs from your run when writing the final observations.

## 16. References

* PyTorch documentation: https://pytorch.org/docs/stable/index.html
* torchvision documentation: https://pytorch.org/vision/stable/index.html
* CIFAR-10 dataset: https://www.cs.toronto.edu/~kriz/cifar.html

---

**Assignment:** 7 – Transfer Learning Model Comparison
**Architectures:** AlexNet, VGG16, ResNet50, EfficientNetB0
**Dataset:** CIFAR-10
**Approach:** Feature-extraction transfer learning
