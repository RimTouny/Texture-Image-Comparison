**Texture Image Comparison**
Exploring texture image processing with the [Kylberg Texture Dataset](https://filedn.com/lkCRue0RhPO7ercIrqFRl2Y/datasets/KylbergTextureDatasetV1/)"subsetOfKylbergTextureDataset-6classes-40samples.zip"The training and validation data are the images numbered 001 to 030, while the testing images have
the numbers 031 to 040, this project covers preprocessing, histogram-based learning-free classification, and a multilayer perceptron approach. Evaluation metrics are applied to training and validation sets, and a thorough comparison of classification methods is presented. Additionally, potential enhancements through additional pyramid levels are discussed. This project holds significance within my Master's in Computer Vision at uOttawa (2023).

- Required libraries: scikit-learn, pandas, matplotlib.
- Execute cells in a Jupyter Notebook environment.
- The uploaded code has been executed and tested successfully within the [Google Colab](https://colab.google/) environment.

## Texture Image Classification 
The dataset comprises 6 classes with 40 images each, divided into training,and testing sets.The images are of size 576 × 576.: canvas1/cushion1 /linsseeds1/sand1/seat2/stone1

## **Key Tasks Undertaken**    
  1. **Image Preprocessing:**
     - Build an image pyramid with 3 levels for each image with downsampling by a factor of 2. and additional processing.The         final image pyramid size should be [576×576, 228×228, 144×144].
         + Sample on linsseeds1 
           <p align="center">
            <img src="https://github.com/RimTouny/Texture-Image-Comparison/assets/48333870/a379934c-3a72-4df6-94a6-  f0f0d6c30bc0"/>
          </p>
     - Utilize the Sobel edge filter on each level of the image pyramid, then summarize the filtered texture image by a     
       histogram with a fixed bin size of 256.
         + Sample on Smoothed Histogram (Level 1) on Training Data
           <p align="center">
            <img src="https://github.com/RimTouny/Texture-Image-Comparison/assets/48333870/6af3f45d-cb07-4680-a3e8-0bfe165d6a76"/>
          </p>

  2. **Learning-Free Classification:**
     - Splitting the training data to train and validuation
     - Use the first pyramid level histogram ([1 × 256]).
     - Generate an overall histogram for each texture category by fusing the histograms from all the textures of the same           category in the training set. This can be done by averaging the histograms in each category.
           <p align="center">
            <img src="https://github.com/RimTouny/Texture-Image-Comparison/assets/48333870/6af3f45d-cb07-4680-a3e8-0bfe165d6a76"/>
          </p>
     - Evaluate on the training and validation sets.
       + Training Set
         <p align="center">
            <img src="https://github.com/RimTouny/Texture-Image-Comparison/assets/48333870/e23a79d6-f355-4d91-928c-307df2868f76"/>
          </p>

       + Validation  Set
         <p align="center">
            <img src="https://github.com/RimTouny/Texture-Image-Comparison/assets/48333870/e082c295-981f-4d10-9a0f-0789d744a97b"/>
          </p>
     - Visualize a miss-classified sample and discuss observations.
       + Training Set
         ```python
            Misclassified samples: [  0   1   2   3   4   5   6   7   8   9  10  11  12  13  14  15  16  17
              18  19  20  21  22  23  24  25  26  27  28  29  30  31  32  33  34  35
              36  37  38  39  40  41  42  43  44  45  46  47  48  49  50  51  52  53
              54  55  56  57  58  59  60  61  62  63  64  65  66  67  68  69  70  71
              72  73  74  75  76  77  78  79  80  81  82  83  84  85  86  87  88  89
              90  91  92  93  94  95  96  97  98  99 100 101 102 103 104 105 106 107
             108 109 110 111 112 113 114 115 116 117 118 119 120 121 122 123 124 125
             126 127 128 129 130 131 132 133 134 135 136 137 138 139 140 141 142 143]
         ```
       + Validation  Set
         ```python
           Misclassified samples: [ 0  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23
           24 25 26 27 28 29 30 31 32 33 34 35]
         ```
  
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

	
