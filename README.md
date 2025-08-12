# Monet CycleGAN for Kaggle's "I'm Something of a Painter Myself" Competition

This repository contains a Jupyter Notebook that implements a CycleGAN (Cycle-Consistent Adversarial Network) to solve the image to image translation challenge from Kaggle's "GANs Getting Started" competition. The primary goal is to transform landscape photographs into new, synthetic images that appear as if they were painted in the style of Claude Monet.

## The Challenge

The core challenge of this Kaggle competition lies in its **unpaired** dataset. The provided data consists of a collection of landscape photographs and a separate collection of Monet's paintings. Crucially, this means there are no direct one to one pairs of a photo and its corresponding Monet style version.

This makes it an ideal problem for a CycleGAN, which is designed specifically to learn mappings between two distinct image domains without requiring paired examples. The model learns not only to translate from Photo -> Monet but also the reverse, Monet -> Photo, enforcing a "cycle consistency" that ensures the translated images retain the core content of the originals.

## Dataset Details

The data for this project is provided by Kaggle and consists of the following:

- **Competition:** GANs Getting Started ("I'm Something of a Painter Myself")
- **Data Source:** [Kaggle GANs Getting Started Competition](https://www.kaggle.com/c/gan-getting-started)
- **Contents:** Two sets of TFRecord files:
    - `monet_tfrec`: 300 paintings by Claude Monet.
    - `photo_tfrec`: 7,038 landscape photographs.
- **Image Specifications:** All images are 256x256 pixels with 3 color channels (RGB).

## Evaluation

Submissions for this competition are evaluated based on the **Fréchet Inception Distance (FID) score**. The FID score is a metric used to assess the quality of images created by a generative model. It compares the statistical distribution of the generated images to that of the real Monet paintings. A lower FID score indicates a higher quality and more realistic set of generated images that are more statistically similar to the target domain.

## Repository Contents

- `week-5-submission.ipynb`: The complete Jupyter Notebook containing the code for data analysis, model architecture, hyperparameter tuning, training, and final image generation.
