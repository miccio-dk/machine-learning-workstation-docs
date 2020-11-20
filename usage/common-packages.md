# Common packages

This page provides support with commonly used python packages and libraries, for tasks such as machine learning, numerical analysis, and data manipulation and visualization.

## Machine Learning

The major machine learning python package is [`sk-learn`](https://scikit-learn.org/stable/). This library provides interfaces and APIs for the most common ML algorithms such as SVM, PCA, linear regression, nearest neighbors, and the likes, as well as functions for data preprocessing, and dataset handling. Moreover, it is designed to work seamlessly with numpy, matplotlib, and others.

## Deep learning

There are many deep learning libraries, such as TensorFlow, Theano, PyTorch, CNTK, or Caffe. These are low-level libraries providing high performances at the price of a steel learning curve.

Most often, it is desirable to use a high-level library which employs any of the above as backends. The most common ones are:

* [`keras`](https://keras.io/): APIs implementing most common neural network building blocks such as dense layers, convolutional layers, LSTM units, batch normalization, and various optimizers \(SGD, Adam, Adagrad...\). Supports TensorFlow, Theano, and CNTK as backends.
* [`fast.ai`](https://docs.fast.ai/): high-level platform based on PyTorch, for easily develop and train deep models using current best practices. The same developer team offers highly accessible [online courses](https://course.fast.ai/) on deep learning.

## Audio processing

* [`libROSA`](https://librosa.github.io/librosa/): audio analysis, feature extraction, music information retrieval
* [`scipy.signal`](https://docs.scipy.org/doc/scipy/reference/signal.html#module-scipy.signal): signal processing, linear time-invariant systems, spectral analysis

## Data manipulation/visualization

* [`pandas`](https://pandas.pydata.org/pandas-docs/stable/): data analysis and manipulation
* [`matplotlib`](https://matplotlib.org/users/index.html): plotting \(similar to MATLAB\)
* [`numpy`](https://www.numpy.org/devdocs/user/quickstart.html): numerical analysis, multi-dimensional matrices and arrays

## Sample conda environment

### Tensorflow/keras

```text

```

