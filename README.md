

# LLM-based Human Activity Recognition for IoT Applications

This repository contains the implementation of Large Language Models (LLMs) for zero-shot Human Activity Recognition (HAR) using IMU sensor data from the HHAR dataset. 
The project evaluates how data preprocessing, feature extraction, and prompt engineering affect both accuracy and inference cost (tokens) using the model GPT-5.

We evaluate GPT-5’s performance when classifying four activities:
- Walking
- Sitting
- Standing
- Biking
The core goal is to measure the trade-off between accuracy and inference cost under different input representations and prompt designs.


## Aim
This project aims to examine the performance of LLM for detecting HAR in the context of IoT while considering the associated inference cost and identifying a balance between accuracy
and cost-efficiency.

## Objectives
- Study the state-of-art in applying LLMs in human activity recognition.
- Determine public datasets that can be used in the evaluation of LLMs activity recognition.
-  Implement and assess an existing LLM using prompts to recognize human activity using
      IoT sensor data.
- Evaluate the performance and cost-efficiency of the LLM model in activity recognition.


## Repository Structure
| File | Description |
|------|-------------|
| 0__overlapping.ipynb | Experiment 1 — HAR using raw IMU data with 0% overlap |
| 50%_Overlapping.ipynb | Experiment 1 — HAR using raw IMU data with 50% overlap |
| feature_extraction.ipynb | Experiment 2 — HAR using six extracted features per window |
| Chain-of-Thought_code.ipynb | Experiment 3 — Prompt engineering: DO vs CoT |
| Dataset | The HHAR dataset used in this project |



## Dataset: HHAR (Heterogeneity Human Activity Recognition)
* IMU time-series data from accelerometer and gyroscope
* Devices: 8 smartphones + 4 smartwatches
* Users: 9 individuals
* Classes/Activities : walk, sit, stand, bike , stairs , stairsdown
* Sampling rate: 50 Hz
* Window size: 2.56 sec (128 samples)



## Methodology Summary
1. Load and clean sensor data
2. Merge accelerometer + gyroscope
3. Segment into windows
4. Prepare prompts
5. Send batches to GPT-5 API
6. Collect predictions and token usage
7. Evaluate using accuracy, precision, recall, F1-score, and confusion matrix




 ## Results Summary
* Best performance achieved using Raw + 0% overlap
* Best cost-efficiency achieved using Feature Extraction
* CoT improves interpretability but increases cost


