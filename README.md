🧠 Handwritten Digit Recognition using CNN (MNIST)

A simple yet powerful Convolutional Neural Network (CNN) model that classifies handwritten digits (0–9) from the MNIST dataset.
This project demonstrates end-to-end deep learning workflow — preprocessing, model building, training, evaluation, and visualization.

📌 Project Overview

This project builds a 3-layer CNN using TensorFlow/Keras to recognize handwritten digits.
MNIST contains 70,000 grayscale images of size 28×28.

The model achieves 98%+ accuracy, making it an ideal beginner-friendly but resume-worthy deep learning project.

🚀 Tech Stack

Python

TensorFlow / Keras

NumPy

Matplotlib

📥 Dataset

MNIST is automatically downloaded through Keras:

(x_train, y_train), (x_test, y_test) = tf.keras.datasets.mnist.load_data()

🛠️ Steps in the Project
1️⃣ Load & Preprocess Data

Normalize pixel values

Reshape images to (28, 28, 1) for CNN input

2️⃣ Build CNN Architecture
model = models.Sequential([
    layers.Conv2D(32, (3,3), activation='relu', input_shape=(28,28,1)),
    layers.MaxPooling2D((2,2)),

    layers.Conv2D(64, (3,3), activation='relu'),
    layers.MaxPooling2D((2,2)),

    layers.Flatten(),
    layers.Dense(64, activation='relu'),
    layers.Dense(10, activation='softmax')
])

3️⃣ Train the Model

Optimizer: Adam

Loss: SparseCategoricalCrossentropy

Epochs: 5

Validation split: 10%

4️⃣ Evaluate
test_loss, test_acc = model.evaluate(x_test, y_test)
print("Test Accuracy:", test_acc)


Expected accuracy: ~98%

5️⃣ Predict & Visualize

Show image + prediction:

plt.imshow(img.reshape(28,28), cmap='gray')
print("Predicted:", np.argmax(prediction))

📊 Results
Metric	Score
Test Accuracy	98%+
Loss	Low & stable

Includes:

Training/Validation Accuracy Curve

Training/Validation Loss Curve

Predictions visualization (input image + output label)

🖼️ Sample Prediction
Input Image: (digit 7)
Predicted Label: 7
Actual Label: 7
<img width="707" height="728" alt="image" src="https://github.com/user-attachments/assets/d7a1da36-8e00-412f-9c0f-e8cdd6f1e147" />
