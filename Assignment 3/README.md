# Assignment 3 - Forward Propagation and Backpropagation

## Aim

To implement forward propagation and backpropagation using TensorFlow/Keras and analyze the effect of different learning rates and number of epochs on model performance.

## Dataset

MNIST handwritten digit dataset.

- Training samples: 60,000
- Testing samples: 10,000
- Image size: 28 × 28
- Number of classes: 10

## Model Architecture

- Input: 28 × 28 pixels
- Flatten layer
- Hidden layer: 128 neurons
- Activation: ReLU
- Output layer: 10 neurons
- Activation: Softmax
- Optimizer: Adam

## Implementation

The assignment demonstrates:

1. Data preprocessing
2. Normalization
3. Forward propagation
4. Loss calculation
5. Backpropagation using GradientTape
6. Model training
7. Learning rate comparison
8. Epoch comparison
9. Accuracy and loss visualization
10. Final model evaluation

## Experiments

### Learning Rates

The following learning rates were compared:

- 0.0001
- 0.001
- 0.01

### Number of Epochs

The following epoch values were compared:

- 3
- 5
- 10

## Evaluation

The model was evaluated using test loss and test accuracy.

## Conclusion

Learning rate and number of epochs significantly affect neural network training. A suitable learning rate provides stable and efficient learning, while an appropriate number of epochs allows the model to learn effectively without unnecessary training.