# AI-Driven Crop Disease Prediction Using the McCulloch-Pitts Neuron Model

Co-authored research on lightweight, interpretable AI for plant disease detection, published by IEEE.

- **Venue:** 2025 9th International Conference on Computing, Communication, Control and Automation (ICCUBEA), Pune, India
- **Publisher:** IEEE (conference proceedings)
- **IEEE Xplore:** https://ieeexplore.ieee.org/document/11284169
- **DOI:** https://doi.org/10.1109/ICCUBEA65967.2025.11284169
- **Authors:** Shraddha Samant, Swati Jagtap, Vahid Shaikh, Saif Shaikh, Suyash Sawant, Yashraj Pangave

## Overview

The paper motivates its approach from two challenges it identifies in crop disease detection: reliance on manual field inspection, and the computational cost of deep learning models such as CNNs, which the authors argue limits their use on low-power devices available to small farms. To explore an alternative, the paper investigates the McCulloch-Pitts Neuron Model (MPNM), one of the earliest mathematical models of a neuron, used as a simple, interpretable, threshold-based classifier for crop disease prediction.

## Approach

The paper describes a system that combines deep feature extraction with a lightweight classical classifier:

1. **Input:** a user uploads a plant leaf image through a web interface; the system validates format and quality, and the design also considers environmental factors such as temperature, humidity, and soil pH as supporting input features.
2. **Preprocessing:** images are resized to 150x150 pixels, normalized, and augmented (rotation, zoom, shift, flip) to improve robustness.
3. **Feature extraction:** a CNN (convolutional layers with 32, 64, and 128 filters, batch normalization, max pooling, and a 512-neuron dense layer with dropout, trained with the Adam optimizer) learns visual features from the leaf images.
4. **Classification:** rather than classifying directly with the CNN, the extracted features are compressed with Principal Component Analysis, scaled, and passed to the McCulloch-Pitts Neuron Model, whose threshold-based binary decision function separates healthy from diseased conditions.
5. **Output:** a web interface prototype presents the predicted disease, a confidence level, and a treatment suggestion.

The design motivation behind this hybrid is interpretability and efficiency: the authors chose the MPNM for its transparent binary logic and low computational cost, with resource-constrained or edge deployment as the intended setting. The paper does not include a measured compute comparison against an end-to-end deep network.

## Dataset

The study uses the Pumpkin Leaf Disease dataset: 2,000 high-resolution images balanced across five classes - Bacterial Leaf Spot, Downy Mildew, Mosaic Disease, Powdery Mildew, and Healthy Leaf (400 images each).

## Findings

The paper reports headline figures of about 96% overall accuracy with precision and recall near 95%, and an inference time of roughly half a second per prediction. It also reports that validation accuracy plateaued at 65-70% and itself identifies overfitting, so how well the approach generalizes to unseen field data is not firmly established by these experiments. A comparison included in the paper reports the MPNM pipeline ahead of a conventional CNN baseline on precision and recall in the authors' setup.

## Limitations and future work

The authors identify overfitting as the main open issue and propose stronger regularization, further data augmentation, and early stopping as next experiments, alongside expanding the dataset beyond pumpkin leaves and extending the system toward mobile deployment.

## Citation

S. Samant, S. Jagtap, V. Shaikh, S. Shaikh, S. Sawant, and Y. Pangave, "AI-Driven Crop Disease Prediction Using the McCulloch-Pitts Neuron Model," in *2025 9th International Conference on Computing, Communication, Control and Automation (ICCUBEA)*, Pune, India, 2025, pp. 1-7, doi: 10.1109/ICCUBEA65967.2025.11284169.

## Scope

This page documents the published research. No source code is included here, and the publisher PDF is not hosted - the official version is available on IEEE Xplore via the link above.
