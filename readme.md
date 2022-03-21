# Setting Up An Evvironment for machine Learning on M1 (with TensorFlow)

### Assumptions & Prereqs
Assuming:
- you are familiar with Git and have already set up a repo and pulled down a new project.
- Brew, Miniforge3, Conda (If you don't have these installed, check out mrdbourke's repo in Sources referenced below.)
- 

### Setting Up A New Python Environment
conda create --prefix ./env python=3.8
conda activate ./env

### Install TensorFlow (for Mac)
conda install -c apple tensorflow-deps
python -m pip install tensorflow-macos
python -m pip install tensorflow-metal

### Install Datasets & Common ML Packages
python -m pip install tensorflow-datasets
conda install jupyter pandas numpy matplotlib scikit-learn

### Register Environment In Jupyter Notebook
python -m ipykernel install --user --name tensorflow --display-name "Python 3.8 (tensorflow)"

### Test the New Environment
Create a new workbook and check that you can select your newly created env, "Python 3.8 (tensorflow)".
In the notebook run this code: 
(it might take a minute or so the first time thru.)

import numpy as np
import pandas as pd
import sklearn
import tensorflow as tf
import matplotlib.pyplot as plt

# Check for TensorFlow GPU access
print(f"TensorFlow has access to the following devices:\n{tf.config.list_physical_devices()}")

# See TensorFlow version
print(f"TensorFlow version: {tf.__version__}")

# DONE

### Sources
https://www.youtube.com/watch?v=_1CaUOHhI6U&t=8s
https://github.com/mrdbourke/m1-machine-learning-test