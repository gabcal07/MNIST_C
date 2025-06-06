# MNIST_C: Neural Network Digit Recognition

A lightweight C implementation of a neural network for handwritten digit recognition using the MNIST dataset. This project provides a simple yet effective command-line tool for training, testing, and applying a neural network model to recognize digits.

## Features

- **Feed-forward neural network** with configurable parameters
- **Training** using backpropagation algorithm
- **Testing** against the MNIST test dataset
- **Recognition** of digits in custom image files
- **Persistence** capabilities to save and load trained models
- **Black & white** image conversion option

## Requirements

- C compiler (gcc recommended)
- MNIST dataset files (not included)
- Standard C libraries

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/MNIST_C.git
   cd MNIST_C
   ```

2. Compile the source code:
   ```bash
   make
   ```

## Usage

The program provides a command-line interface with the following commands:

```
USAGE:
  ./neural <command> [options]

COMMANDS:
  learn      Train the neural network with specified parameters
  test       Evaluate the network's performance on test data
  learnTest  Train the network and then test its performance
  apply      Recognize a digit in the specified image file

OPTIONS:
  learning_rate  Learning rate (default: 0.3) - Controls step size during training
  attempts       Number of training iterations (default: 2)
  blackNwhite    Use black and white conversion [0|1] (default: 1)
  path           Path to image file for digit recognition
```

### Examples

```bash
# Train with learning rate 0.1, 5 iterations, B&W mode
./neural learn 0.1 5 1

# Test pre-trained network using B&W mode
./neural test 1

# Train and test with specified parameters
./neural learnTest 0.2 3 1

# Recognize digit in the specified image
./neural apply digit.png 1
```

## Architecture

The neural network consists of:

- **Input Layer**: 784 neurons (representing a 28x28 pixel image)
- **Hidden Layer**: 300 neurons
- **Output Layer**: 10 neurons (one for each digit 0-9)

The network uses the sigmoid activation function and is trained using backpropagation with a configurable learning rate.

## File Structure

- `Neural.c/h`: Main neural network implementation
- MathTools.h: Mathematical functions for neural network operations
- Persist.h: Functions for saving and loading trained models
- DataLoad.h: Functions for loading MNIST data and processing images

## Performance

On the MNIST test dataset, the network can achieve accuracy rates that vary based on training parameters. With optimal settings, it can reach significant accuracy while maintaining computational efficiency.
