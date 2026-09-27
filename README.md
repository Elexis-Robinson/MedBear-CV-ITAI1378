# MedBear-CV-ITAI1378

## Project Information

**Project:** MedBear Computer Vision Medication Verification  
**Student:** Elexis Robinson  
**Course:** ITAI 1378 Computer Vision and AI  
**Tier:** Tier 1: CORE — This project uses one computer vision classification model to recognize a controlled set of pill appearances, with application logic that uses confidence scores to verify or reject uncertain predictions

## Problem Statement

Medication organizers and automated dispensers can support medication adherence, but they do not always verify that the physical pill being presented or dispensed matches what the system expects. Patients, caregivers, and healthcare technology developers need additional safeguards that can help identify possible medication mismatches before a pill is accepted or dispensed.

## Solution Overview

MedBear is an AI-assisted medication adherence system that uses computer vision to recognize and verify a controlled set of pill appearances. The computer vision component will capture a pill image, preprocess it, predict the pill class with a confidence score, and either verify the result or reject and flag an uncertain prediction.

**Input → Model → Output**

Pill Image → Preprocessing → Computer Vision Model → Predicted Pill Class + Confidence Score → Verify or Reject

## Technical Approach

The primary computer vision task is **fine-grained multiclass image classification**. I plan to use transfer learning with a pretrained convolutional neural network rather than training a model from scratch.

The project will use Python with a deep-learning framework such as PyTorch or TensorFlow, along with OpenCV for image processing and Google Colab for development and training. Transfer learning is appropriate because the project focuses on a limited set of visually defined pill classes and must be achievable using free computing resources within one semester.

## Data Plan

The project will use a combination of public and custom pill-image data.

### NIH/NLM C3PI
C3PI provides controlled reference images and consumer-quality pill images that can support pill-recognition research.

### OGYEIv2
OGYEIv2 contains 4,480 images representing 112 pill classes under controlled imaging conditions and multiple lighting conditions.

### Custom MedBear Dataset
Later in development, I will capture images using the actual MedBear prototype camera. These images will vary lighting, rotation, distance, position, and partial occlusion so the model can be evaluated under conditions closer to the final device environment.

ePillID may also be evaluated as an additional benchmark dataset.

For the first working model, I plan to narrow the project to approximately **5–12 visually defined pill classes, targeting around 8 classes**. Classes will represent specific pill appearances rather than medication names alone because manufacturer, dosage, imprint, shape, and color can change how a medication looks.

## Success Metrics

**Primary metric:** Target a **macro F1 score of at least 0.85** on a held-out evaluation set.

**Secondary metric:** Target **inference under 1 second per image** during the prototype computer vision workflow.

Additional evaluation will include a confusion matrix, per-class precision and recall, and analysis of low-confidence or rejected predictions.

## Milestone Plan

### Blueprint
Finalize project scope, technical approach, data sources, success metrics, risks, and GitHub structure.

### First Working Demo
Run a pretrained computer vision model end-to-end on a small number of sample pill images to confirm the pipeline works before beginning heavy data preparation or training.

### Make It Yours
Select the initial MedBear pill classes, prepare the C3PI and/or OGYEIv2 data, fine-tune the model, and add confidence-based verification and rejection logic.

**Capstone alignment:**
- Data Pipeline and Exploratory Analysis: October 3
- Working AI Model: October 31

### Improve and Measure
Evaluate performance using held-out and custom images, record metrics, analyze confusion between difficult classes, and improve robustness under different imaging conditions.

**Capstone alignment:**
- Integrated System Prototype: November 21

### Package and Present
Complete the demonstration workflow, documentation, GitHub repository, final presentation, and demo video.

**Capstone alignment:**
- Final Project Delivery: December 5
- Final Presentation: December 10

## Risks and Plan B

### Risk 1: Visually Similar Pills

Some pills may have very similar colors, shapes, or sizes, which could cause the model to confuse classes.

**Plan B:** Reduce the initial class set, prioritize visually distinguishable classes, use image augmentation, analyze the confusion matrix, and reject low-confidence predictions rather than forcing a classification.

### Risk 2: Public Data Does Not Match the MedBear Camera

Public dataset images may look different from images captured inside the physical MedBear prototype.

**Plan B:** Capture a small custom dataset using the actual MedBear camera and use those images for testing and supplemental training.

## Resources and Estimated Cost

- Google Colab
- Python
- PyTorch or TensorFlow
- OpenCV
- GitHub
- Raspberry Pi and camera hardware already available for MedBear
- HCC fabrication and prototyping resources

**Estimated software and compute cost: $0** using free educational and cloud resources.

## Responsible AI

MedBear is an educational and research prototype. It is not a clinical diagnostic system and is not intended to replace pharmacists, physicians, or other healthcare professionals. Uncertain predictions will be rejected or flagged rather than automatically treated as correct.
