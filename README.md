# MedBear-CV-ITAI1378

## Team Members

- Elexis Robinson

## Project Tier

**Tier 1: CORE** — This project uses one computer vision classification model to recognize a controlled set of pill appearances, with application logic that uses confidence scores to verify or reject uncertain predictions.

## Problem Statement

Medication organizers and automated dispensers can support medication adherence, but they do not always verify that the physical pill being presented or dispensed matches what the system expects. Patients, caregivers, and healthcare technology developers need additional safeguards that can help identify possible medication mismatches before a pill is accepted or dispensed.

## Solution Overview

MedBear is an AI-assisted medication adherence system that uses computer vision to recognize and verify a controlled set of pill appearances. The computer vision component will capture a pill image, preprocess it, predict the pill class with a confidence score, and either verify the result or reject and flag an uncertain prediction.

**Input → Model → Output**

Pill Image → Preprocessing → Computer Vision Model → Predicted Pill Class + Confidence Score → Verify or Reject

## Technical Approach

- **CV Technique:** Fine-grained multiclass image classification
- **Model Architecture:** Convolutional Neural Network (CNN)
- **Model:** ResNet50
- **How I will use it:** Transfer learning on a controlled set of pill-image classes
- **Framework:** PyTorch
- **Development Environment:** Google Colab
- **Additional Tools:** Python, OpenCV, GitHub

Transfer learning is appropriate because the project focuses on a limited set of visually defined pill classes and can adapt a pretrained image model without training from scratch. This approach also keeps the project achievable using free computing resources within one semester.

## Dataset

The project will use a combination of public and custom pill-image data.

### NIH/NLM C3PI

- **Source:** NIH/NLM C3PI
- **Data:** Controlled reference images and consumer-quality pill images
- **Use:** Public pill-image source for model development and evaluation
- **Link:** [ADD PUBLIC DATASET LINK]

### OGYEIv2

- **Source:** OGYEIv2
- **Size:** 4,480 images
- **Classes:** 112 pill classes
- **Use:** Controlled pill images captured under multiple imaging conditions
- **Link:** [ADD PUBLIC DATASET LINK]

### Custom MedBear Dataset

Later in development, I will capture images using the actual MedBear prototype camera. These images will vary lighting, rotation, distance, position, and partial occlusion so the model can be evaluated under conditions closer to the final device environment.

ePillID may also be evaluated as an additional benchmark dataset.

For the first working model, I plan to narrow the project to approximately **5–12 visually defined pill classes, targeting around 8 classes**. Classes will represent specific pill appearances rather than medication names alone because manufacturer, dosage, imprint, shape, and color can change how a medication looks.

## Success Metrics

- **Primary:** Measure macro F1 score with a target of at least **0.85** on a held-out evaluation set.
- **Secondary:** Measure inference speed with a target of **under 1 second per image**.

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

## Resources

- **Compute:** Google Colab
- **Framework:** PyTorch
- **Libraries/Tools:** Python, OpenCV, GitHub
- **Hardware:** Raspberry Pi and camera hardware already available for MedBear
- **Additional Resources:** HCC fabrication and prototyping resources
- **Estimated Cost:** $0 using free-tier and open-source resources

## Risks and Mitigation

| Risk | Probability | Plan B |
|---|---|---|
| Visually similar pills may be confused by the model | Medium | Reduce the initial class set, prioritize visually distinguishable classes, use augmentation, analyze the confusion matrix, and reject low-confidence predictions rather than forcing a classification |
| Public dataset images may not match the MedBear camera environment | Medium | Capture a small custom dataset using the actual MedBear camera for testing and supplemental training |

## Responsible AI

MedBear is an educational and research prototype. It is not a clinical diagnostic system and is not intended to replace pharmacists, physicians, or other healthcare professionals. Uncertain predictions will be rejected or flagged rather than automatically treated as correct.

## Demo Video

Link will be added at the Final.

## AI Usage Log

See `docs/AI_usage_log.md`.

## Current Status

- [x] Repository created
- [ ] Proposal submitted
- [ ] First working demo
- [ ] System works on my data
- [ ] Metrics measured
- [ ] Final submitted
