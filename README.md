# Deep Dream with TensorFlow and InceptionV3

This project implements Deep Dream using TensorFlow 2 and a pre-trained InceptionV3 model. It amplifies specific neuron activations to produce surreal, dream-like transformations of input images.

---

## Overview

Deep Dream is a technique to visualize what convolutional neural networks "see" by modifying an image to enhance features that activate specific layers. Instead of training a model, we optimize the input image using gradient ascent.

---

## Features

- Uses TensorFlow 2.x and Keras API
- Based on pre-trained InceptionV3
- Mid-level feature layer selection (`mixed3`, `mixed5`)
- Normalized gradient ascent steps
- Image saving and visualization utilities

---

## Installation

Clone the repository:

```bash
git clone https://github.com/Priyav78/Deep-Dream.git
cd Deep-Dream
```

Install dependencies:

```bash
pip install tensorflow numpy pillow matplotlib
```

---

## Usage

Run the script:

```bash
python deep_dream.py
```

This will:
- Download a sample image
- Apply 100 gradient ascent steps
- Save and display `dream_result.jpg`

To use your own image, replace the image URL or load a local file in the `__main__` block.

---

## Output Example

Before:
![Original](https://storage.googleapis.com/download.tensorflow.org/example_images/YellowLabradorLooking_new.jpg)

After Deep Dream:
![Dreamed](images/dream_result.jpg)

---

## Code Structure

- `load_image(path)` - Preprocesses image for InceptionV3
- `layer_loss(img, model)` - Computes total activation across chosen layers
- `deepdream_step(img, model, step_size)` - Applies one gradient ascent step
- `run_deepdream(img, steps, step_size)` - Iteratively enhances the image
- `deprocess(img)` - Converts tensor back to image format
- `save_and_show(img, fname)` - Saves and displays the final result

---

## Customization

- **Layers**: Modify `layer_names = ['mixed3', 'mixed5']` to change dream depth
- **Steps**: Adjust `steps=100` for more or less effect
- **Step Size**: Modify `step_size=0.01` for intensity control

---

## License

This project is for educational and experimental use. Pre-trained model credits go to TensorFlow and the original Deep Dream authors.

---

## Acknowledgments

- Google Deep Dream (original concept)
- TensorFlow team for model and framework support
