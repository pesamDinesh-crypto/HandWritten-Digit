✍️ Handwritten Digit Recognition using CNN

A Handwritten Digit Recognition project built with Python, TensorFlow/Keras, CNN, Tkinter, NumPy, PIL, SciPy, and Matplotlib.

The application allows users to draw a handwritten digit on a graphical interface and uses a trained Convolutional Neural Network (CNN) to recognize the digit from 0 to 9.

🚀 Project Overview

This project uses the MNIST handwritten digit dataset to train a CNN model.

The application provides a simple Tkinter GUI where users can:

✍️ Draw a digit using the mouse
🔮 Predict the handwritten digit
📊 View prediction probabilities
🎯 View prediction confidence
🧹 Clear the drawing and try another digit
🤖 Automatically train the model if a saved model does not exist

The trained model is saved as:

digit_recognition_model.h5
🧠 Technologies Used
Technology	Purpose
Python	Main programming language
TensorFlow	Deep learning framework
Keras	CNN model development
MNIST	Handwritten digit dataset
NumPy	Numerical and array operations
Tkinter	Graphical User Interface
PIL/Pillow	Image processing
SciPy	Image shifting and preprocessing
Matplotlib	Prediction probability visualization
🏗️ CNN Model Architecture

The project uses the following CNN architecture:

Input Image
    ↓
Conv2D - 32 Filters
    ↓
MaxPooling2D
    ↓
Conv2D - 64 Filters
    ↓
MaxPooling2D
    ↓
Flatten
    ↓
Dense - 128 Neurons
    ↓
Dropout - 0.5
    ↓
Dense - 10 Neurons
    ↓
Softmax
    ↓
Digit Prediction (0-9)
Model Configuration
optimizer = "adam"
loss = "sparse_categorical_crossentropy"
epochs = 15
batch_size = 128
validation_split = 0.1
📂 Project Structure
Handwritten-Digit-Recognition/
│
├── handwritten digit.ipynb
├── digit_recognition_model.h5
├── README.md
└── requirements.txt

digit_recognition_model.h5 is generated automatically after the model is trained.

⚙️ How the Project Works
1. Load MNIST Dataset

The project loads the MNIST dataset using TensorFlow/Keras:

from tensorflow.keras.datasets import mnist

(x_train, y_train), (x_test, y_test) = mnist.load_data()

The images are reshaped to:

28 × 28 × 1

and normalized between 0 and 1.

2. Train the CNN

If the model file does not exist, the CNN is trained automatically.

MNIST Dataset
      ↓
Image Preprocessing
      ↓
CNN Training
      ↓
Model Saved
      ↓
digit_recognition_model.h5

If the model already exists, training is skipped.

3. Draw a Digit

The Tkinter application provides a 200 × 200 canvas.

The user can draw a digit using the mouse.

+--------------------+
|                    |
|        7           |
|                    |
|                    |
+--------------------+

   [ Predict ] [ Clear ]
4. Image Preprocessing

The drawn image goes through several preprocessing steps.

Drawn Image
     ↓
Grayscale Conversion
     ↓
Image Inversion
     ↓
Resize to 28 × 28
     ↓
Noise Thresholding
     ↓
Normalization
     ↓
Centering / Shifting
     ↓
CNN Model

The preprocessing function converts the image into the format expected by the MNIST-trained CNN:

(1, 28, 28, 1)
5. Digit Prediction

The CNN produces probabilities for all ten digits:

0 → Probability
1 → Probability
2 → Probability
...
9 → Probability

The digit with the highest probability is selected using:

pred = np.argmax(probs)

The confidence is calculated as:

confidence = probs[pred] * 100
6. Confidence Check

The project uses a 70% confidence threshold.

If confidence is below 70%:

Unclear, try again

Otherwise, the application displays:

Prediction: 7 (98.43%)
7. Probability Visualization

After prediction, Matplotlib displays a bar chart showing the probability for each digit from 0 to 9.

Example:

Probability
   |
1.0|             █
   |             █
0.8|             █
   |             █
0.6|             █
   |             █
0.4|     █       █
   |     █       █
0.2| █   █   █   █
   +--------------------
     0 1 2 3 4 5 6 7 8 9
🖥️ Application Features
✍️ Drawing Canvas

Users can draw handwritten digits directly inside the Tkinter window.

🔮 Predict Button

Processes the drawing and predicts the digit.

🧹 Clear Button

Clears the canvas and allows another digit to be drawn.

📊 Probability Chart

Displays the model's probability for each digit.

🎯 Confidence Score

Displays the confidence of the predicted digit.

💾 Automatic Model Saving

The trained model is saved as:

digit_recognition_model.h5

The next time the application runs, the saved model can be loaded instead of retraining.

📦 Installation

Clone the repository:

git clone https://github.com/YOUR-USERNAME/Handwritten-Digit-Recognition.git

Move into the project directory:

cd Handwritten-Digit-Recognition

Install the required libraries:

pip install numpy tensorflow pillow scipy matplotlib

Tkinter is normally included with Python on Windows.

▶️ Run the Project

Open the notebook:

jupyter notebook

Then open:

handwritten digit.ipynb

Run the code.

Alternatively, you can convert the notebook into a Python file and run it with Python.

📋 Requirements

Create a requirements.txt file containing:

numpy
tensorflow
pillow
scipy
matplotlib
📸 Project Workflow
                MNIST Dataset
                     │
                     ▼
              CNN Model Training
                     │
                     ▼
          digit_recognition_model.h5
                     │
                     ▼
              Tkinter Application
                     │
                     ▼
              User Draws Digit
                     │
                     ▼
              Image Preprocessing
                     │
                     ▼
                  CNN Model
                     │
                     ▼
             Prediction + Confidence
                     │
                     ▼
             Probability Visualization
🎯 Example Output

When a user draws a digit:

Prediction: 5 (97.82%)

If the model confidence is below the threshold:

Unclear, try again
💡 Key Learning Outcomes

Through this project, I worked with:

Python programming
Deep Learning
Convolutional Neural Networks
TensorFlow and Keras
MNIST dataset
Image preprocessing
NumPy arrays
Tkinter GUI development
Model saving and loading
Prediction probabilities
Confidence-based prediction
Matplotlib visualization
🔮 Future Improvements

Possible improvements include:

Improve the GUI design
Add model accuracy evaluation
Add prediction history
Add an option to save drawings
Improve preprocessing for different handwriting styles
Add multiple-digit recognition
Add real-time prediction
Deploy the model as a web application
👨‍💻 Author

Pesam Dinesh

Skills Demonstrated
Python
TensorFlow
Keras
Machine Learning
Deep Learning
CNN
NumPy
Pandas
Tkinter
Pillow
SciPy
Matplotlib
