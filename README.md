Low-Light Face Mask Detection
📖 Introduction
Face mask detection became one of the most critical computer vision problems in 2020 with the onset of the COVID-19 pandemic. Detecting individuals with or without masks in public areas is vital for public health safety. However, one of the major struggles in this domain is detecting face masks in non-ideal environments that are poorly suited for standard computer vision tasks.

This project aims to tackle that challenge by focusing on detecting face masks in darkened, distorted, and blurred environments using advanced feature extraction and machine learning techniques.

🎯 Project Aim and Objectives
While standard systems perform well in bright, clear conditions, their accuracy drops significantly in the dark. By utilizing computer vision techniques like feature extraction and image classification, this system accurately and efficiently identifies individuals' mask-wearing compliance, even under difficult lighting.

Key Objectives:
Data Augmentation: Create a darkened, distorted, and blurred dataset from an existing baseline dataset to simulate poor environmental conditions.

Face Extraction: Extract human faces from the altered images using bounding box annotations.

Feature Extraction: Apply Gabor filters to capture textural and frequency features from the faces.

Model Comparison: Train and compare machine learning algorithms (Random Forest and Support Vector Machines) to evaluate their accuracy on the altered dataset.

⚙️ Methodology & Approach
Our pipeline consists of several distinct stages:

Dataset Preparation:

The base dataset contains 853 images categorized into 3 distinct classes: Wearing Mask, Not Wearing Mask, and Not Wearing Mask Correctly.

To optimize computational time, we sample a random subset of 100 images.

Image Alteration:

We use OpenCV and NumPy to artificially darken, blur, and distort the images to simulate challenging environments.

Face Cropping:

Using the provided dataset annotations, we isolate and extract only the human faces from the altered images.

Feature Extraction:

We utilize the Gabor filter, a linear filter highly effective at detecting edge and texture frequencies in images, making it an excellent choice for identifying the structural presence of a face mask.

Model Training:

Extracted features are fed into Random Forest and SVM classifiers. Both models are trained and tested on our altered dataset.

📊 Evaluation Protocol
To ensure the reliability and effectiveness of our solution, we follow a strict evaluation framework:

Metrics: We use scikit-learn metrics to generate the Accuracy and Confusion Matrix for both models.

Error Analysis: We conduct a deep dive into misclassified instances to understand the specific conditions where the models fail.

Model Comparison: The Random Forest and SVM models are directly compared based on two primary factors: overall accuracy and computational time consumption.

Baseline for Success: The minimum expected accuracy for this project is >70%. Anything below this threshold is considered a failure given the difficulty of the darkened data.
