# Part 1: Neural Network Fundamentals and Training Analysis

This project builds a feed-forward neural network using TensorFlow/Keras to predict whether a customer is likely to cancel their subscription (churn) based on their behavior, plan features, and satisfaction scores.

## Project Structure
- `notebook.ipynb`: The interactive lab report containing data exploration, preprocessing, network training, and evaluations.
- `requirements.txt`: List of dependencies required to execute the workspace code.
- `results/`: Subfolder containing our performance metrics graphs and parameter experiments table.

## Key Technical & Analytical Explanations

### 1. Role of Weights and Biases
- **Weights:** These function as importance dials for each raw feature input. If the model finds out that `satisfaction_score` drastically impacts a customer's decision to leave, it scales that feature's connection weight up. If an input column does not impact churn, its weight dial is turned down towards zero.
- **Biases:** These act as individual offset thresholds. They allow the neural network to shift the internal data triggers up or down, making sure neurons fire only when a precise mix of criteria is reached.

### 2. Why an Activation Function is Required
Without activation functions (like **ReLU**), a neural network would only perform basic straight-line math calculations ($y = wx + b$), meaning it could only act as a simple linear classifier. Real-world customer patterns are far more complex and winding. Activation functions introduce non-linearity, allowing the system to match nuanced rules such as: *"If a customer's tenure is short AND support tickets are high, churn risk jumps exponentially."*

### 3. Impact of Learning Rates
- **Too High:** If the learning rate speed setting is dialed up too aggressively, the network's optimization process goes out of control. It overshoots the correct weight answers wildly, causing the network model to collapse or yield erratic results.
- **Too Low:** If it is set too low, adjustments are microscopic. The model takes a very long time to finish learning and easily gets stuck in subpar mathematical zones before finding the right solution.

### 4. Overfitting vs Underfitting Analysis
Our trained network model demonstrates a healthy, balanced fit. The training error/accuracy and testing error/accuracy track close together over the training epochs. Because the test scores mirror our training metrics instead of dropping off, it proves that the network successfully generalized its knowledge to new data rather than simply memorizing the training records.
