# AI-Powered Traffic Management System - Experimentation

This repository serves as a research and experimentation log for an AI-powered traffic management system. It captures the iterative development process across multiple computer vision and machine learning components used for intelligent traffic monitoring and management.

The repository currently consists primarily of Jupyter notebooks, each corresponding to a specific subsystem or experimental direction explored during the project.

This repo is intended to:

* Preserve the learning and experimentation journey

* Document architectural and model-level decisions

* Serve as a reference point when converting experiments into modular or production-ready systems later

* High-Level System Vision

The broader goal of the project is to build an AI-driven traffic management pipeline capable of:

* Detecting traffic rule violations (helmet, seatbelt)

* Identifying vehicles and extracting license plate numbers

* Tracking vehicles across frames

* Predicting traffic congestion and delays

* Providing human-readable explanations using LLMs

The system blends:

* Computer Vision (YOLOv8, Mask R-CNN, OCR)

* Tracking (DeepSORT)

* Classical ML (XGBoost)

* Large Language Models (Mistral / Phi)

* Decision-support logic for traffic authorities

This repository focuses on the model experimentation layer, not deployment or UI.

## Repository Structure & Notebook Themes
### 1. Helmet Detection

Notebooks in this section explore:

* Training YOLOv8 models for helmet detection

* Dataset preprocessing and annotation strategies

* Class definitions (helmet, rider, plate)

* Performance evaluation and failure cases

Key focus:

* Understanding how well object detection models handle small objects and occlusions in traffic scenes

* Comparing results across different training runs and hyperparameters

### 2. Seatbelt Detection

This set of notebooks focuses on:

* YOLOv8-based seatbelt detection

* Handling subtle visual cues (seatbelt vs no seatbelt)

* Dataset balancing and label noise

* Testing detection robustness under different lighting conditions

* Seatbelt detection was treated as a harder visual classification problem due to:

* Small visual features

* Variability across vehicle types and camera angles

### 3. License Plate Detection & Recognition

These notebooks cover two stages:

* License plate detection (YOLOv8)

* License plate recognition (EasyOCR)

Experiments include:

* Cropping detected plates

* Text extraction and post-processing

* Error patterns in OCR outputs

* Simulated storage of recognized plates

This component is critical for:

* Vehicle identification

* Violation attribution

* Downstream automation (e.g., challan generation)

### 4. TrafficLLM / Traffic Prediction Experiments

This section documents experimentation with LLMs for traffic prediction and explanation, including:

* Few-shot prompting for traffic congestion reasoning

* Supervised fine-tuning (SFT) using traffic datasets

Hybrid approaches combining:

* XGBoost for numeric prediction

* LLMs for natural language explanations

Key themes:

* Limitations of LLMs for raw time-series prediction

* Strengths of LLMs as explanation and decision-support layers

* Prompt engineering vs fine-tuning trade-offs

This experimentation ultimately informed a hybrid ML + LLM architecture.

## Important notes:

* Notebooks are not perfectly linear

* Some approaches were explored and later abandoned

* Redundant experiments are intentionally preserved

