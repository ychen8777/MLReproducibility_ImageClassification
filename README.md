# Reproducing the results of "Automatic classification of volcanic rocks from thin section images using transfer learning networks"

## Scope of Reproducibility
Polat et al. tested two convolutional neural networks (CNNs) with transfer learning with the goal of distinguishing between six volcanic rock types based on thin section image data collected using a petrographic microscope(1). We reproduced a subset of their results and conducted ablation experiments to examine ways to improvement.

## Methodology
We adapted the authors' Python script and executed it using two different techniques. The evaluation of the DenseNet121 model was performed in a Google Colab notebook (connected to a Deep Learning VM on Google Cloud Platform with 4 CPUs, 15GB of RAM, and a NVIDIA Tesla T4 GPU with 16GB GPU memory,) and experiments of ResNet50 was run in a locally hosted Anaconda environment (using a local NVIDIA GForce RTX 2080 Super). 

## Datasets
The subject of the images that we wish to classify is different volcanic rocks. In order to observe and identify the minerals, they are sampled and shaped into thin sections. Each picture is taken using Nikon Coolpix P5100 digital camera system attached to a Nikon Eclipse 50i POL type binocular research microscope. The 12 megapixel camera generates images of 4000*3000 pixels. The data set used in this study was custom made by the researchers of Polat et al. and can be downloaded at this link https://drive.google.com/drive/folders/12cVpuVQw6sS7ZXMChRdyQNht4b4E_Pvq. It consists of 1200 images of thin sections evenly distributed among 6 labels resulting in 200 images per label. 

The split of the training and test sets is 70% training and 30% testing. Elements are randomly chosen when generating the training set. Each image is resized to 224*224 pixels for use in the model. They are then normalized vis a vis the largest individual value in the image. The authors did not mention any validation set used. 

## Results
For the subset of experiments we chose to examine, we were able to reproduce the average accuracies reported by the authors to within 1%. Furthermore, our computing time was similar to that reported in their methods section. Thus, we validated the conclusion that transfer learning using DenseNet121 and ResNet50 is an efficient, high accuracy method of classification for the task. Our targeted experiments also reaffirmed that, while DenseNet121 outperforms ResNet50 by ~1%, they both perform exceedingly well, and ResNet50 is more efficient in running time.

![DenseNet121_plots](/figures/DenseNet121_plots.jpg)
![ResNet50_plots](/figures/ResNet50_plots.jpg)
![Accuracy_summary](/figures/Average_Accuracy_Summary.jpg)
