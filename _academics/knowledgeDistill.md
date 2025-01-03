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
TinyML is an emerging field for on device machine learning.  Using knowledge distillation from a Wav2Vec2-base teacher model and two student models of varied reduced sizes, we focused on the impact of time series data in the distillation pipeline.  We finetuned Wav2Vec2-base (95M parameters) using the Speech Emotion Recognition (SER) dataset TESS to a 98.3% accuracy.  Knowledge from this teacher model was distilled to Wav2Small (90K parameters) at a 94.8% accuracy and our Wav2Tiny (15K parameters) at a 86.3% accuracy.  

![Image description](/assets/img/academics/knowledgeDistill/modelsTable_results.png){:.lead width="700" height="600"}

SER Models
{:.figcaption}

## Research Problem
The device emitted unique LED color patterns to convey internal state changes as it performed the vertical profile, as it loses Bluetooth connection once submerged in water.  The internal state machine consists of pumping water into the floater bladder on a timed interval, just until it begins to sink, then it automatically shuts off the pump and freefalls.  It registers when it has reached the bottom, sits there for an additional timed interval, and then begins pumping water out to return to the surface and automatically shuts the pump off when emptied.  Throught this profile, it is displaying different colors indicating these internal changes, as well as collecting temperature, depth, and pressure data.  

It transmits all of the collected data via Bluetooth to the command station laptop, which then gets written to a csv file and plotted on the GUI automatically. 

## Setting & Related Work
Our team was one of the few teams in the competition to collect all of the Float Task points.  It is a category in the MATE ROV Competition that is notoriously difficult due to the 15' depth and the stringent requirements at the more difficult competition level. 

## Methodology
- Automated vertical profile
- Embedded State Machine
- Bluetooth control and data transmission
- Automated data saving and plotting

## Experiments & Results
- PyQt
- Arduino Nano
- Arduino Bluetooth Module
- RTC Clock
- Bluerobotics sensor

## Insights
- C++
- Python

## Key References
![Image description](/assets/img/projects/floater/floater_stateMach_umlDiag_700w_533h.png){:.lead width="700" height="533"}

Arduino Nano embedded State Machine.
{:.figcaption}

## Project Presentation
![Image description](/assets/img/projects/floater/floater_GUI_1136w_901h.png){:.lead width="800" height="635"}

Floater GUI
{:.figcaption}

Our team name was "The Vikings"; the pixelart graphic assets for the GUI were created using generative AI.  

## Project Report
