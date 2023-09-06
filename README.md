# DynamicDet
Reimplementation of a paper DynamicDet: A Unified Dynamic Architecture for Object Detection in colab. The architecture is inspired by CBNet, uses CBNet's DHLC module to embed the multi-scale features. The architecture has two detectors (detector1 and detector2) and one router (router).

Implementation of a papar DynamicDet: A Unified Dynamic Architecture for Object Detection

By: Monye Babatunde.
subject: Computer vision.

Here is a concise:
The paper proposes DynamicDet, a novel dynamic neural network framework for efficient and accurate object detection. The key ideas are:

1) Carefully designed dynamic architecture based on the nature of object detection.
2) An adaptive router to analyze multi-scale features and automatically decide the inference route.
3) Optimization strategy with custom exiting criterion based on detection losses.
4) Variable-speed inference for a wide range of accuracy-speed trade-offs with a single model.
This is PyTorch implementing of the paper dynamicDet for object detection. The overall architecture consists of two detectors and one router.

The first backbone extracts multi-scale features from the input image, which are fed to the router. The router predicts a difficulty score for the image.

The architecture is inspired by CBNet and designed based on the nature of object detection. The composite connection uses CBNet's DHLC module to embed the multi-scale features into the second backbone.

If the image is classified as "easy" by the router, detection results come from the first detector. If it is "hard", the multi-scale features are enhanced by the second backbone, and detection results come from the second detector.

This allows for trade-offs between computation (speed) and accuracy. "Easy" images are processed by only one backbone, while "hard" images utilize two backbones.

The router automatically decides the inference route based on the predicted difficulty score, enabling adaptive computation for each input image.

This is what was done

PyTorch Framework & Object Detection: The code is in PyTorch and aimed at object detection. ✅

Two Detectors and One Router: The architecture has two detectors (detector1 and detector2) and one router (router). ✅

Inspired by CBNet: The architecture uses a CBNet-like DHLC module to combine features from two backbones. ✅

Router Decides Inference Score: The router uses the output of the second block of merged backbones to decide the difficulty score. ✅

First Backbone for Initial Features: The first backbone (backbone1_block1 and backbone1_block2) extracts multi-scale features that are then used by the router to decide the difficulty score. ✅

Composite Connection with DHLC: The DHLC module combines multi-scale features from the first and second backbones. ✅

Trade-offs Between Speed and Accuracy: If the router classifies an image as "easy," only the first detector is used. If the image is "hard," the second backbone enhances the features and uses the second detector. This is a computational trade-off. ✅

Results Based on Router's Classification: The code uses detector1 for easy images and detector2 for hard ones, as decided by the router. ✅

However, the author used the COCO dataset while I PASCAL dataset for ease of training.
I'd say the code satisfies all requirements.
