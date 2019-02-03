# Fashion_MNIST

Dimensionality-reduction + ConvNet example
---
1. I am considering imbalanced binary classification problem of classifying images from the Fashion-MNIST data-set (https://github.com/zalandoresearch/fashion-mnist) as bags (8th class) or not-bags (i.e. any other of the 10 classes).

2. As an interesting constraint, I am allowed to select only 20 features from the 28x28 = 784 dimensions that each image belongs to.

Solution found in this repo consists of four jupyter-notebooks:

desc | link | note
--- | --- | --- 
**Encode the images to 20 dims.** Train the appropriate decoders at the same time. | https://github.com/olszewskip/Fashion_MNIST/blob/master/dimensionality_reduction.ipynb | An **autoencoder** does better than **PCA**.
Save the decoded images to files. | https://github.com/olszewskip/Fashion_MNIST/blob/master/compression.ipynb | The classifier will be fit without modifying the decoder, hence we can decode once before further training.
Train a **convolutional network**. Compare results of various encoders | https://github.com/olszewskip/Fashion_MNIST/blob/master/classification.ipynb | PCA can be as good as an overcomplicated autoencoder, but it does not win.
Score the best model on test-data | https://github.com/olszewskip/Fashion_MNIST/blob/master/final_test.ipynb | **97% F1** in 'bag'-class.

The notebooks were run on Colab.

All files, including the intemediate data, are here: https://drive.google.com/open?id=1DbbL4hL1qKrXEjbaDUxGxp--n20Bl0oH .

#### TODO:
* The project lacks a simple baseline. One should try to use PCA(20) with a random-forest on top or something similar, to get a better feeling how crucial the deep-learning is in this case.
* Make a t-SNE plot.
