# Introduction

The primary objective of this project is to develop a robust system that can automatically detect signatures in documents/cheques and determine their authenticity. By extracting and comparing embeddings, the system can accurately identify whether a given signature matches any of the signatures in a dataset containing different individuals signatures


# Solution Overview
<p align="center">
  <img src="https://github.com/VishwaKarthikeyan/Experiment/blob/main/arch/arch_sign.PNG" alt="image" width="800" height="auto">
</p>


**Signature Object Detection with YOLO**: We use the YOLO algorithm, known for its efficiency and accuracy, to detect signatures within document and cheque images. YOLO's ability to perform real-time object detection makes it ideal for our application, ensuring quick and reliable signature localization.

**Embedding Extraction**: Once the signatures are detected, the next step involves extracting their embeddings. These embeddings are high-dimensional feature vectors that capture the unique characteristics of each signature.

**Similarity Comparison**: To determine the authenticity of a signature, we compare the embeddings of the detected signatures with those from a reference dataset containing signatures from various individuals. By calculating the cosine similarity between embeddings, we can measure the degree of similarity and make an informed decision about whether the detected signature matches any signature in the dataset.


# Models Used

**YOLO (You Only Look Once**): Used for real-time signature detection in document images.

**MobileNet-v2**: Generates high-dimensional feature vectors (embeddings) from signatures for similarity comparison and authentication.

# Training

## YOLO (Signature Detection)

**Data**: Consists of annotated images containing signatures. Annotations include bounding box coordinates and class labels (signature).
Model

**Model**: YOLO (You Only Look Once) is a convolutional neural network (CNN) designed for real-time object detection. It typically consists of multiple convolutional layers followed by fully connected layers to predict bounding boxes and class probabilities.

**Hyper-parameters**

**No. of Epochs** : 100

**imgsz** : 640

## MobileNet-v2

**Data**: Consists of images of signatures from various individuals for embedding extraction model training.

**Model**: The model used is MobileNetV2, adapted for embedding extraction. It is pretrained on large datasets and fine-tuned on images of signatures to extract discriminative features.


# Evaluation Metrics

## YOLO (Signature Detection)

**Precision** : 0.998

**Recall** : 1.0

**MAP50** : 0.995

**MAP50-95** : 0.983
