# Nightscale-Image-Colorization-cGAN
1.Overview:


ColorizeGAN is a deep learning project that applies Conditional Generative Adversarial Networks (cGANs) for automatic image colorization. Given a grayscale image, the model predicts plausible and realistic color versions, learning both global semantics and fine texture details. The generator creates colorized outputs conditioned on grayscale inputs, while the discriminator ensures that the generated colors are visually convincing and consistent with real images. This method effectively bridges the gap between low-level luminance patterns and high-level contextual color understanding, producing photo-realistic colorizations.


**2. Motivation:**


Image colorization is an inherently ill-posed problem — a single grayscale image may correspond to multiple valid color interpretations. Traditional methods often rely on user hints, reference images, or heuristic-based algorithms, which are limited and time-consuming.With GAN-based learning, we can learn the colorization process directly from large-scale image datasets.
The model naturally discovers contextual color associations such as:
   1. Skies tend to be blue.
   2. Vegetation appears in shades of green.
   3. Skin tones and materials have natural color ranges.
This fully data-driven approach enables automatic, realistic, and context-aware colorization without any manual color guidance.


**3. Architecture:**

ColorizeGAN is built on the Conditional GAN (cGAN) architecture, which conditions both the generator and discriminator on grayscale input.


**Generator**


Based on a U-Net encoder-decoder structure. Captures both global context and local spatial details. Skip connections preserve fine structures and edges during upsampling.



**Discriminator**
A CNN trained to distinguish real color images from generated ones. Takes grayscale + color pairs as input. Guides the generator toward producing more realistic color distributions.


**Loss Function**


The training objective combines:
     1.Adversarial Loss — encourages natural, photo-realistic color outputs.
     2.L1 Reconstruction Loss — enforces pixel-level accuracy to maintain structural consistency.
     3.This combination ensures that generated images are both realistic and faithful to the input grayscale structure.


**4. Dataset**


ColorizeGAN can be trained on standard large-scale image datasets such as:
     1.Places365
     2.ImageNet
     3.MS COCO
Each training image is converted to grayscale for input, while its original color version serves as the target. This allows the model to learn grayscale-to-color mappings in a supervised learning setup.
For domain-specific applications, smaller datasets (e.g., portraits, landscapes, historical photos) can be used to fine-tune the model’s color style.




**5. Results**
After sufficient training, the model produces vivid, context-aware colorizations that align with real-world expectations. Input (Grayscale)	Output (Colorized)
**.Observed behavior:**


  1.Skies are rendered in natural blue tones.
  2.Vegetation and water appear in realistic green and aqua hues.
  3.Human faces and objects display balanced, lifelike colors.
These results show the power of conditional adversarial training in learning color semantics directly from data.


**6. How to Run**


1. Clone the Repository
2. cd ColorizeGAN
3. Install Dependencies: pip install -r requirements.txt
4. Run the Notebook
jupyter notebook Image_Colorization_using_condGAN.ipynb

 
 
 7.Dependencies


Python ≥ 3.8, TensorFlow / PyTorch, NumPy, Matplotlib, OpenCV,Jupyter Notebook
 


**8.Related Work**

    1. Isola et al., Image-to-Image Translation with Conditional Adversarial Networks, CVPR 2017

    2. Goodfellow et al., Generative Adversarial Nets, NeurIPS 2014

    3.Zhang et al., Colorful Image Colorization, ECCV 2016

**Acknowledgements**

This project was inspired by the growing interest in image-to-image translation and color restoration using deep neural networks. Special thanks to the open-source ML community for providing resources and pretrained models that helped in experimentation.
