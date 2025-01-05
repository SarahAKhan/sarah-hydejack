---
layout:      project
title:       UDA for Personalized Action Recognition in Body Gesture Control for Mobile Robotics
date:        2024-12-08
image:
  path:       /assets/img/academics/roboUDA/udaCoverGraphic_1920w.png
  srcset:
    1920w:   /assets/img/academics/roboUDA/udaCoverGraphic_1920w.png
    960w:    /assets/img/academics/roboUDA/udaCoverGraphic_960w.png
    480w:    /assets/img/academics/roboUDA/udaCoverGraphic_480w.png
full_width: true
caption:     Mobile robot gesture recognition using Unsupervised Domain Adaptation.
description: >
  Robot gesture recognition (non-verbal gesture communication) research project centered on adapting perception domain to Anki Vector robot using Unsupervised Domain Adaption.
featured:    true
---
## Unsupervised Domain Adaptation for Personalized Action Recognition in Body Gesture Control for Mobile Robotics
 Human-Robot Interaction necessitates robot perception of human gestures and physical behaviors from the unique field view of the robot.  While recent developments in gesture recognition have yielded robust models capable of extracting human pose features in complex disorganized environments, recognition is often not extended to the varying domains of mobile robot perception. Leveraging recent advancements in Unsupervised Domain Adaptation (UDA), we have developed a perspective-aware action classifier (PAAC) that integrates UDA with keypoint-based feature extraction to enhance action recognition across mobile robot perspectives and domains. Comprised of a multilayer perceptron and adversarial domain discriminator, PAAC demonstrates significant adaptive abilities over the base RTMO gesture recognition in the mobile robot domain.

## Context & Motivations
Integrating the MMPose (RTMO) ML model and the Anki Vector Robot, we constructed a pose estimation pipeline for the Vector robot, having adapted the model's domain to the small mobile robot's perception using Unsupervised Domain Adaptation (UDA).  The purpose of this project was to enable gesture recognition in the Vector robot for the purposes of human gesture based non-verbal communication and interaction.  We sought to address the following challenges:

- Perspective shift
- Lack of data from Vector robot perspective
- Customizable actions
- Improve gesture perception generalizability
- Data generation with low resource needs
- Customizable gestures commands
- Command registering using keypoint features

![KD models metrics and parameters](/assets/img/academics/roboUDA/perspectiveShift_motivations_graphic_960w450h.png)

Impact of perspective shift on key-point based action recognizer
{:.figcaption}

### Relevant Works

## Methodology

### Gesture Class with Vector Responses

### RTMO Backbone

## Results

## Limitations & Conclusions