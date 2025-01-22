# Contributing Guidelines

Thank you for your interest in contributing! This document outlines the requirements for submitting model configurations.

## Pull Request Requirements

Each PR should only contain a single YAML config. When submitting a model configuration YAML file, please ensure it meets the following criteria are met for the metadata:

1. **author**: Must match your GitHub username.
2. **task**: Must match the folder name containing the YAML file.
3. **keywords**: 
    - Must be a non-empty list of strings.
    - All keywords must be lowercase.
    - Include keywords that make your config special such as "small_object_detection", "attention" etc.
4. **description**: 
    - Must be a non-empty string.
    - Maximum 1000 words.
5. **min_version**: Must be a valid Ultralytics package version.
6. **flops** and **parameters**: You can get this using `model.info()` in Ultralytics.
7. **strides**: Must match the computed stride values. If you don't know this, you can submit leave it blank and the GitHub Actions will comment on your PR with the correct value which you can use to update.
8. **nc** (number of classes): Must be a positive integer.

### Automated Checks

The PR will be automatically checked for:
- Valid model loading
- Matching FLOPs and parameters
- Correct stride values
- Valid metadata fields

If any discrepancies are found, a comment will be posted on your PR with the actual vs. expected values.

### Example Configuration

```yaml
# Metadata
author: username
task: classify
keywords: [cnn, convnext]
description: ConvNeXt-Tiny pretrained backbone with Classify head.
flops: 73.7
parameters: 28805473
min_version: 8.3.59

# Model configuration
nc: 1
strides: [32]
backbone:
  - [-1, 1, TorchVision, [768, "convnext_tiny", "DEFAULT", True, 2]]
head:
  - [-1, 1, Classify, [nc]]
```

### Post-Merge Actions

Once your PR is successfully merged, a GitHub discussion thread will be automatically created and you will be tagged as the author to keep you updated on any feedback or questions from the community.