# PRODIGY_GA_04

##  Project Overview
This project demonstrates **Image‑to‑Image Translation** using a **conditional Generative Adversarial Network (cGAN)** called **pix2pix**.  
By training on paired datasets, the model learns to translate input images (e.g., edges, sketches, grayscale) into target outputs (e.g., realistic photos, colored versions).

##  Features
- Implementation of pix2pix using TensorFlow/Keras
- Paired dataset integration (train/test splits)
- Generator (U‑Net) and Discriminator (PatchGAN) architectures
- Training with checkpoints for reproducibility
- Example outputs showcasing translated images

##  Repository Structure
- `data/` → Paired training and testing datasets
- `models/` → pix2pix model definitions (generator & discriminator)
- `checkpoints/` → Saved model weights during training
- `results/` → Generated image samples
- `requirements/` → Dependencies file
- `README.md` → Project documentation

## Workflow -
- Install dependencies 
- Configure Kaggle API 
- Organize dataset - Define U-Net generator 
- Train and save checkpoints 
- Generate and visualize results ## Dataset Setup 
- Download the facades dataset from [Kaggle](https://www.kaggle.com/datasets/sabahesaraki/pix2pix-facades-dataset). 
- Place training images in `data/train/` and test images in `data/test/`. - `.gitkeep` files are placeholders to keep the folder structure visible in GitHub.


## Sample Output
![output](results/samples/output_1.png)

##  Example Usage
```python
import tensorflow as tf
from models.pix2pix import Generator, Discriminator

# Load dataset (example)
train_dataset = tf.data.Dataset.list_files("data/train/*.jpg")

# Initialize models
generator = Generator()
discriminator = Discriminator()

# Example: generate output from an input image
input_image = tf.io.read_file("data/test/pair_1.jpg")
input_image = tf.image.decode_jpeg(input_image)
input_image = tf.expand_dims(input_image, 0)

generated_output = generator(input_image, training=False)
```

##  Results

Here are some example outputs generated after training pix2pix:

**Input (edges):**  
`edges image`

**Generated Output (photo):**  
`translated photo`

---

Sample outputs are stored in the `results/samples/` folder for reference.

##  Repository Structure 
```
PRODIGY_GA_04/
├── data/
│   ├── train/
│   └── test/
├── models/
│   └── pix2pix.py
├── checkpoints/
│   └── latest/
├── results/
│   └── samples/
│       ├── output_1.png
│       ├── output_2.png
│       └── ...
├── requirements/
│   └── requirements.txt
└── README.md
```
