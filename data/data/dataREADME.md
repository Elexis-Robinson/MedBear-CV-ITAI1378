# MedBear Computer Vision Data Plan

## Project Scope

The MedBear computer vision project will use pill-image data to train and evaluate a model that recognizes a controlled set of visually defined pill classes.

For the first version, I plan to use approximately 5–12 pill classes, targeting around 8 classes so the project remains achievable within the semester.

## Planned Data Sources

### NIH/NLM C3PI

C3PI includes controlled reference pill images and consumer-quality images. I plan to evaluate this dataset as a source of images for model development and testing.

### OGYEIv2

OGYEIv2 contains 4,480 images across 112 pill classes. I plan to select a smaller subset of relevant classes rather than using the entire dataset.

### Custom MedBear Images

Later in development, I plan to collect a small custom dataset using the actual MedBear prototype camera. Images will include variations in:

- Lighting
- Rotation
- Distance
- Pill position
- Partial occlusion

These images will help evaluate whether the model performs well under conditions closer to the physical MedBear device.

### Additional Benchmark

ePillID may also be evaluated as an additional pill-identification benchmark if needed.

## Labels

Each class will represent a visually defined pill appearance. Labels will account for characteristics such as shape, color, imprint, dosage, and manufacturer when those characteristics affect appearance.

## Data Preparation Plan

Before heavy training, I will first inspect a small sample of the available data to confirm image quality, labeling, class availability, and overall feasibility.

The selected data will later be separated into training, validation, and test sets so model performance can be evaluated on images it has not seen during training.

## Current Status

- [x] Public dataset sources identified
- [ ] Dataset links added
- [ ] Initial classes selected
- [ ] Sample images reviewed
- [ ] Training, validation, and test split created
- [ ] Custom MedBear images collected
