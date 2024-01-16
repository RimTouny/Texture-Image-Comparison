# **Texture Image Comparison**
Exploring texture image processing with the Kylberg Texture Dataset, this project covers preprocessing, histogram-based learning-free classification, and a multilayer perceptron approach. Evaluation metrics are applied to training and validation sets, and a thorough comparison of classification methods is presented. Additionally, potential enhancements through additional pyramid levels are discussed. This project holds significance within my Master's in Computer Vision at uOttawa (2023).

- Required libraries: scikit-learn, pandas, matplotlib.
- Execute cells in a Jupyter Notebook environment.
- The uploaded code has been executed and tested successfully within the [Google Colab](https://colab.google/) environment.

## Texture Image Classification 
The dataset comprises 6 classes with 40 images each, divided into training, and testing sets: canvas1/cushion1 /linsseeds1/sand1/seat2/stone1

## **Key Tasks Undertaken**
  1. **Image Preprocessing:**
     - Build an image pyramid for each image with downsampling and additional processing.
     - Apply Sobel edge filtering and generate histograms with a fixed bin size of 256.
     - Visualize an example of the processed image in the notebook.
  
  2. **Learning-Free Classification:**
     - Use the first pyramid level histogram ([1 × 256]).
     - Generate overall histograms for each texture category based on training set data.
     - Visualize the six histograms for each category.
     - Define a function to measure distance and classify unseen images.
     - Evaluate on the training and validation sets, analyzing accuracy, recall, and precision.
     - Visualize a miss-classified sample and discuss observations.
  
  3. **Learning-Based Classification:**
     - Build an MLP model with scikit-learn or Keras API.
     - Flatten the input feature from shape [3 × 256] to [1 × 768].
     - Train the classifier using the validation set.
     - Evaluate on the training and validation sets, analyzing accuracy, recall, and precision.
  
  4. **Classification Comparison:**
     - Compare classifiers from Sections 1.3 and 1.4 on the test data subset.
     - Consider performance, training effort, prediction speed, generalization, and robustness.
     - Provide a brief discussion based on quantifiable criteria.
  
  5. **Improved Classification:**
     - Show histograms for the second and third levels of the pyramid.
     - Discuss the potential impact of additional pyramid levels on classification improvement.
     - Support the discussion with diagrams and/or numbers.
