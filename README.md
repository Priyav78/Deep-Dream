Deep Dream with TensorFlow and InceptionV3

This project demonstrates how to use a pre-trained convolutional neural network to generate Deep Dream images. By amplifying the activations of specific intermediate layers in the InceptionV3 model, the script reveals the features the network "sees" and enhances them to produce surreal, dream-like visuals.

Overview
Deep Dream is a visualization technique that modifies an input image to maximize neuron activations in a neural network. Rather than training the network, the input image itself is adjusted using gradient ascent to exaggerate patterns recognized by the model.

Features
Uses TensorFlow 2.x and Keras APIs

Based on pre-trained InceptionV3 model

Selects intermediate layers for texture-rich enhancements

Normalizes gradients and image values for stability

Includes utilities to load, process, display, and save results

Requirements
Python 3.7+

TensorFlow 2.x

NumPy

Pillow

Matplotlib

Install dependencies:

bash
Copy
Edit
pip install tensorflow numpy pillow matplotlib
Usage
Run the script directly:

bash
Copy
Edit
python deep_dream.py
This will:

Download a sample image

Run Deep Dream for 100 steps

Save and display the result as dream_result.jpg

Code Structure
load_image() – Loads and preprocesses the input image.

layer_loss() – Calculates the dream score by summing selected layer activations.

deepdream_step() – Performs a single gradient ascent step on the image.

run_deepdream() – Repeatedly applies gradient ascent to amplify features.

deprocess() – Converts the image back to RGB format for saving.

save_and_show() – Saves and displays the final image.

Customization
Replace the sample image with your own by modifying the image URL or path.

Adjust layer_names to dream with different InceptionV3 layers.

Tune steps and step_size for more or less intense dreaming.

License
This project is for educational and experimental purposes. Attribution to original Deep Dream authors and TensorFlow model contributors is acknowledged.
