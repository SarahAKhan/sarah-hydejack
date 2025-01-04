---
layout:      project
title:       Knowledge Distillation for TinyML/Embedded AI
date:        2024-12-09
image:
  path:       /assets/img/academics/knowledgeDistill/KD_pipeline_1920w.png
  srcset:
    1920w:   /assets/img/academics/knowledgeDistill/KD_pipeline_1920w.png
    960w:    /assets/img/academics/knowledgeDistill/KD_pipeline_960w.png
    480w:    /assets/img/academics/knowledgeDistill/KD_pipeline_480w.png
full_width: true
caption:     Model distillation research project using Wav2Vec2-base and time series data.
description: >
  We sought to analyze the impact of time series data in the model distillation pipeline.  Using Wav2Vec2-base as the teacher model (95M parameters) and the TESS dataset, we distilled learning to two student models, Wav2Small (90K parameters) and our Wav2Tiny (15K parameters).
featured:    true
---

## Knowledge Distillation for TinyML/Embedded AI: Model Distillation with Time Series Data
TinyML is an emerging field for on device machine learning.  Using knowledge distillation from a Wav2Vec2-base[1] teacher model and two student models of varied reduced sizes, we focused on the impact of time series data in the distillation pipeline.  We finetuned Wav2Vec2-base (95M parameters) using the Speech Emotion Recognition (SER) dataset TESS to a 98.3% accuracy.  Knowledge from this teacher model was distilled to Wav2Small (90K parameters) at a 94.8% accuracy and our Wav2Tiny (15K parameters) at a 86.3% accuracy.  

![KD models metrics and parameters](/assets/img/academics/knowledgeDistill/modelsTable_results.png){:.lead width="700" height="600"}

SER Models
{:.figcaption}

## Research Problem
Machine Learning has enabled an unprecedented level of device intelligence in recent years and with the various model types available, that intelligence can be tailored to a variety of tasks and insights.  Our interest lay in the exploration of deploying machine learning models directly onto small scale devices themselves.  Due to the often heavy computational costs involved, we investigated TinyML techniques geared towards model scale reduction while maintaining performance accuracy with a focus on time series data.  Time series data in the context of Speech Emotion Recognition (SER) presents a unique challenge as a classification task, as it necessitates the categorization of potentially subjective classifications over continuously distributed data. 

## Setting & Key Related Works
### Teacher Model: Wav2Vec2
As mentioned, we used Wav2Vec2-base as our teacher model, a transformer model capable of a variety of tasks using raw audio data sampled at 16kHz.  The base version had been trained on a large generalized audio dataset, which we then finetuned for the SER task.  The model is capable of achieving high classification accuracy with limited avialable data, with reported results demonstrating this capacity with as little as one hour of audio data.[1]  

![Teacher model training results and parameters](/assets/img/academics/knowledgeDistill/TeacherModel_graphic_1920w2000h.png){:.lead width="700" height="600"}

Wav2Vec2 Teacher Model training results and hyperparameters
{:.figcaption}

### Student Model 1: Wav2Small[2]
A key reference for our project was the research done by the [audEERING](https://www.audeering.com/) group on knowledge distillation and their development of the Wav2Small model architecture, which consists of a VGG7-based convolutional encoder with input normalization, LogMel filter bank generation, pooling layers, and a global mean pooling layer.  We adapted this model with a linear classification head.  The spectrogram layer converts the raw audio into a time-frequency represenatation by applying the Short-Time Fourier Transfomr (STFT), which is then converted into a log-mel spectrogram.  The log-mel spectrogram is then passed through the vgg7 block for feature extraction.

![Student model training results and parameters](/assets/img/academics/knowledgeDistill/StudentModel_wav2Small_graphic_960w1000h.png){:.lead width="700" height="600"}

Wav2Small Student Model architecture and hyperparameters
{:.figcaption}

### Student Model 2: Wav2Tiny
Leveraging the insights provided in [2] on the advantages of the vgg7 approach to audio feature extraction combined with the simplified classification task, we further experimented with our own variation of a reduced model size, which we dubbed Wav2Tiny. This second student model resulted in around 15K parameters.

![Wav2Tiny Student Model architecture](/assets/img/academics/knowledgeDistill/StudentModel_wav2tiny_graphic_1440w1500h.png)

Wav2Tiny Student Model architecture
{:.figcaption}

### Dataset: TESS
The TESS dataset was used to finetune the Wav2Vec2 teacher model for the SER classfication task.  It consists of seven emotion classifications: anger, disgust, fear, happiness, pleasant surprise, sadness, and neutral and with 2800 total datapoints, was split with 2240 samples for training and 560 samples for testing.  The samples themselves are high quality audio recordings in a .wav format. 

### Core Works Referenced
Since this was an introductory TinyML project, we sourced informative learning references for foundational theory, as well as broad ranging TinyML papers surveying applications[5] in order to gain a better understanding of the core principles and current status of the topics.  Hinton, et al's seminal work on knowledge distillation, "Distilling the Knowledge in a Neural Network"(2015) [[4]](http://arxiv.org/abs/1503.02531) is often cited as a core methodology establishing piece, demonstrating the effectiveness of the teacher/student learning paradigm.  As mentioned in other sections [2] also served as a main reference for our student models and their architecture design for lightweight handling of time series data.

## Methodology
The main distillation pipeline was constructed using the finetuned teacher model, a trainer class, the two interchangeable student models, and the TESS Dataset.  

## Experiments & Results


## Insights
- C++
- Python


## Project Report
![Image description](/assets/img/projects/floater/floater_GUI_1136w_901h.png){:.lead width="800" height="635"}

Floater GUI
{:.figcaption}

Our team name was "The Vikings"; the pixelart graphic assets for the GUI were created using generative AI.  

## Key References
1. A. Baevski, H. Zhou, A. Mohamed, and M. Auli, "wav2vec 2.0: A framework for self supervised learning of speech representations," in Proceedings of the 34th Conference on Neural Information Processing Systems (NeurIPS 2020), Vancouver, Canada, 2020. [1](https://arxiv.org/abs/2006.11477)

2. D. Kounades-Bastian, O. Schrüfer, A. Derington, H. Wierstorf, F. Eyben, F. Burkhardt, and B. W. Schuller, "WAV2SMALL: Distilling Wav2Vec2 to 72K Parameters for Low-Resource Speech Emotion Recognition," arXiv preprint arXiv:2408.13920, 2024. [2](https://arxiv.org/abs/2408.13920)

3. Datafuse Analytics, "KNOWLEDGE DISTILLATION ultimate GUIDE," YouTube, 2023.[3](https://youtu.be/708ku_bNJGw?si=Gws8MiAZlB_tYYcW)

4. Hinton, G., Vinyals, O., & Dean, J., "Distilling the Knowledge in a Neural Network," arXiv preprint arXiv:1503.02531, 2015. [4](http://arxiv.org/abs/1503.02531)

5. Gou, J., Yu, B., Maybank, S. J., & Tao, D., "Knowledge Distillation: A Survey," arXiv preprint arXiv:2006.05525, 2021.[5](http://arxiv.org/abs/2006.05525)
