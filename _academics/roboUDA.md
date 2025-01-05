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
 With a central focus of Human-Robot Interaction, this project aims to evaluate the impact of perspective domain shift in small mobile robots, using the Anki Vector and the MMPOSE/RTMO gesture recognition backbone.  We generated Vector domain specific data in order to successfully implement Unsupervised Domain Adaptation (UDA) on RTMO and created unique gesture based responses on Vector. Our results explore the broader implications of robot perception domains and means of integration with modern computer vision. 

## Context & Motivations
Integrating the MMPose (RTMO) ML model and the Anki Vector Robot, we constructed a pose estimation pipeline for the Vector robot, having adapted the model's domain to the small mobile robot's perception domain using Unsupervised Domain Adaptation (UDA).  The purpose of this project was to enable gesture recognition in the Vector robot for the purposes of human gesture based non-verbal communication and interaction.  We sought to address the following challenges:

- Perspective shift
- Lack of data from Vector robot perspective
- Customizable actions
- Improve gesture perception generalizability
- Data generation with low resource needs
- Customizable gestures commands
- Command registering using keypoint features

![Vector robot perspective domain](/assets/img/academics/roboUDA/perspectiveShift_motivations_graphic_960w450h.png){:.lead width="960" height="450"}

Vector robot perspective domain
{:.figcaption}

### Relevant Works
The RTMO backbone leveraging the MMPOSE toolkit served as a fundamental starting point for this project [2-3].  RTMO builds on the RTMPose architecture and is state of the art in terms of general body pose recognition.  We referenced [4] and [1] to develop a deeper understanding of the domain shifts and [5] in terms of developing domain specific gesture data. 

## Methodology
We devised a collection of 7 gesture classifications, which we then recorded using the Vector robot.  Since Anki is no longer in operation, we relied on user created tools such as the Vector [Wirepod](https://github.com/kercre123/wire-pod) for establishing wireless communication with Vector and the unofficial [Python SDK](https://github.com/anki/vector-python-sdk) to gain access to Vector's features and controls.  I automated temporal data collection on Vector using custom image capturing at 8 fps. 

![Vector gesture data generation implementation results](/assets/img/academics/roboUDA/vectorGestureCaptureImages_graphic_1080w506h.png){:.lead width="1080" height="506"}

Vector perspective domain data generation
{:.figcaption}

### Gesture Class with Vector Responses
We recorded the following gesture data classifications for the UDA implementation:

- Both Hands Raised
- Squat
- Crossing Arms (No)
- Circle Above Head (Yes)
- 1 Hand Raised
- Legs in Superhero Pose (A-Frame)
- Wave Single Hand (Goodbye)

With the RTMO model adapted to our gesture classifications, I then developed custom responses on Vector using the [Vector Python SDK](https://github.com/anki/vector-python-sdk).  Vector would exhibit a unique combination of physical movements, utterances, and graphic display on his screen for each classification.

![Vector gesture responses with gesture diagrams](/assets/img/academics/roboUDA/gestureDiagram_graphic_960w450h.png){:.lead width="960" height="450"}

Vector gesture responses with gesture diagrams
{:.figcaption}

![Vector responses and display screen graphic projections to classifications](/assets/img/academics/roboUDA/gestureClassifications_faceGraphic_900w450h.png){:.lead width="900" height="450"}

Vector behavioral responses and display screen graphic projections to gesture classifications
{:.figcaption}

### RTMO Backbone + Perspective Aware Classification
The [RTMO](https://mmpose.readthedocs.io/en/latest/model_zoo_papers/algorithms.html#rtmo) model that served as our backbone came pretrained on generalized gesture data using keypoint features and had extensive recognition capabilities.  It is capable of gesture recognition in crowds and partial image gesture recognition. An adversarial domain dischriminator was added to impelement the UDA.  

## Results

## Limitations & Conclusions

## Key References
1.  D. Kim, K. Wang, K. Saenko, M. Betke, and S. Sclaroff, “A unified framework for domain adaptive pose estimation,” arXiv preprint arXiv:2204.00172, 2022. [1](https://arxiv.org/abs/2204.00172)
2.  T. Jiang, P. Lu, L. Zhang, N. Ma, R. Han, C. Lyu, Y. Li, and K. Chen,“Rtmpose: Real-time multi-person pose estimation based on mmpose,” arXiv preprint arXiv:2303.07399, 2023.[2](https://arxiv.org/abs/2303.07399)
3. T. Jiang, X. Xie, and Y. Li, “Rtmw: Real-time multi-person 2d and 3d whole-body pose estimation,” arXiv preprint arXiv:2407.08634, 2024.[3](https://arxiv.org/abs/2407.08634)
4. K. Zhang, B. Scholkopf, K. Muandet, and Z. Wang, “Domain adaptation under target and conditional shift,” in International Conference on Machine Learning, 2013, pp. 819–827. [4](https://proceedings.mlr.press/v28/zhang13d.pdf)
5. A. Kollakidou, F. Haarslev, C. Odabasi, L. Bodenhagen, and N. Kr¨uger,“Hri-gestures: Gesture recognition for human-robot interaction,” in Proceedings of the 17th International Joint Conference on Computer Vision, Imaging and Computer Graphics Theory and Applications (VISIGRAPP 2022) - Volume 5: VISAPP, 2022, pp. 559–566. [5](https://portal.findresearcher.sdu.dk/en/publications/hri-gestures-gesture-recognition-for-human-robot-interaction)