# Reproducing the results of "Automatic classification of volcanic rocks from thin section images using transfer learning networks"

## Scope of Reproducibility
Polat et al. tested two convolutional neural networks (CNNs) with transfer learning with the goal of distinguishing between six volcanic rock types based on thin section image data collected using a petrographic microscope(1). We reproduced a subset of their results and conducted ablation experiments to examine ways to improvement.

## Methodology
We adapted the authors' Python script and executed it using two different techniques. The evaluation of the DenseNet121 model was performed in a Google Colab (connected to a Deep Learning VM on Google Cloud Platform with 4 CPUs, 15GB of RAM, and a NVIDIA Tesla T4 GPU with 16GB GPU memory,) and experiments of ResNet50 was run in a locally hosted Anaconda environment (using a local NVIDIA GForce RTX 2080 Super). 




