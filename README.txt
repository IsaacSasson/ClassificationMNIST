# Neural Network From Scratch - MNIST Digit Recognition

## Project Overview
This project implements a simple neural network from scratch using NumPy to classify handwritten digits from the MNIST dataset. The neural network uses fundamental linear algebra concepts to demonstrate how machine learning algorithms work at their core, without relying on deep learning frameworks.

## Team Members and Contributions
- **Aaila**: Forward propagation implementation
- **Ikey**: Backpropagation implementation
- **Lucas**: Gradient descent implementation

## Mathematical Concepts Used
This project applies several key linear algebra and calculus concepts:
- Matrix multiplication for layer transformations
- Activation functions (ReLU, Softmax)
- Gradient descent optimization
- Backpropagation for computing gradients
- One-hot encoding for categorical data

## Network Architecture
- Input layer: 784 neurons (28x28 pixel images flattened)
- Hidden layer: 10 neurons with ReLU activation
- Output layer: 10 neurons with Softmax activation (one for each digit 0-9)

## Implementation Details

### Data Preparation
- MNIST dataset loading and preprocessing
- Normalization of pixel values (0-255 → 0-1)
- Splitting into training and development sets
- One-hot encoding of labels

### Neural Network Components
1. **Parameter Initialization**
   - Random initialization of weights
   - Zero initialization of biases

2. **Forward Propagation**
   - Matrix multiplication of inputs by weights
   - Addition of bias terms
   - Application of activation functions (ReLU, Softmax)

3. **Backpropagation**
   - Computation of output layer error
   - Propagation of error to hidden layer
   - Calculation of gradients for all parameters

4. **Parameter Updates**
   - Updating weights and biases using calculated gradients
   - Learning rate control

### Training Process
The model trains through gradient descent over multiple epochs, progressively improving accuracy from approximately 9% to 89% over 500 iterations.

## Results
The final model achieves approximately 89% accuracy on the development set after 500 iterations with a learning rate of 0.1.

## Usage
To run this neural network:

```python
# Clone the repository
# Install required packages: numpy, pandas, matplotlib

# Load and prepare the data
data = pd.read_csv('train.csv')
# (Follow data preparation steps in the notebook)

# Train the model
W1, b1, W2, b2 = gradient_descent(X_train, Y_train, 500, 0.1)

# Make predictions
Z1, A1, Z2, A2 = forward_prop(W1, b1, W2, b2, X_test)
predictions = get_predictions(A2)
```

## Future Improvements
- Add regularization to prevent overfitting
- Implement additional hidden layers
- Experiment with different activation functions
- Add batch processing for more efficient training
- Try different optimization algorithms beyond basic gradient descent

## References
- MNIST dataset: http://yann.lecun.com/exdb/mnist/
- NumPy documentation: https://numpy.org/doc/
- Neural Networks and Deep Learning by Michael Nielsen