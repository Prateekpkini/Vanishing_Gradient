# Vanishing_Gradient
 Visualizing the Vanishing Gradient Problem
A hands-on, educational TensorFlow/Keras demonstration that visually proves why deep neural networks struggle with the Vanishing Gradient Problem and how modern activation functions solve it.

This project trains two deep neural networks on the MNIST dataset side-by-side—one using Sigmoid and one using ReLU—and actively tracks the gradient flow backward through the layers during training.

 Overview
In deep learning, gradients are the "feedback" the model uses to update its weights. If this feedback gets too small as it travels backward through the layers, the earliest layers stop learning. This script acts as a scientific experiment to demonstrate this phenomenon.

By running this code, you will generate visual proof of:

The Whisper Effect (Sigmoid): How Sigmoid squishes gradients, causing them to decay exponentially (vanish) before reaching the first layers.

The Megaphone Effect (ReLU): How ReLU maintains strong, healthy gradient flow throughout the entire depth of the network.

 Features
Custom Gradient Tracker: Uses a custom tf.keras.callbacks.Callback and tf.GradientTape to spy on and record the mean absolute gradients for each layer at the end of every epoch.

Side-by-Side Comparison: Simultaneously builds, trains, and evaluates two identical 5-layer Feed-Forward Neural Networks (differing only by activation function).

Rich Visualizations:

Logarithmic line charts showing gradient decay layer-by-layer.

Validation accuracy comparison curves.

A Seaborn Heatmap Confusion Matrix for the winning model.

 Requirements
To run this project, you will need Python 3.7+ and the following libraries:

Bash
pip install tensorflow numpy pandas matplotlib seaborn scikit-learn
 Usage
Simply clone the repository and run the Python script. The dataset will download automatically (if not already cached), and training will begin.

Bash
git clone https://github.com/prateekpkini/vanishing-gradient-demo.git
cd vanishing-gradient-demo
python main.py
 What You Will See
When you run the script, it will generate three main plots:

Gradient Magnitudes (Log Scale): You will see the Sigmoid model's early layers drop drastically toward zero, while the ReLU model's layers remain grouped and stable.

Accuracy Curves: A clear graph showing ReLU rapidly mastering the dataset while Sigmoid stagnates.

Confusion Matrix: A detailed grid showing exactly which digits the winning ReLU model still occasionally confuses (e.g., mistaking a messy '4' for a '9').

 Educational Value
Perfect for deep learning beginners, students, and educators who want to move beyond the theory and actually see the math of backpropagation breaking down and being fixed in real-time.