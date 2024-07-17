# Introduction

The primary objective of this project is to develop a robust system that can automatically detect signatures in documents/cheques and determine their authenticity. By extracting and comparing embeddings, the system can accurately identify whether a given signature is genuine or forged.


# Solution Overview
<p align="center">
  <img src="https://github.com/VishwaKarthikeyan/Experiment/blob/main/arch/arch_sign.PNG" alt="image" width="800" height="auto">
</p>


**Signature Object Detection with YOLO**: We use the YOLO algorithm, known for its efficiency and accuracy, to detect signatures within document and cheque images. YOLO's ability to perform real-time object detection makes it ideal for our application, ensuring quick and reliable signature localization.

**Embedding Extraction**: Once the signatures are detected, the next step involves extracting their embeddings. These embeddings are high-dimensional feature vectors that capture the unique characteristics of each signature.

**Similarity Comparison**: To determine the authenticity of a signature, we compare the embeddings of the detected signatures with those from a reference dataset containing both real and forged signatures. By calculating the cosine similarity between embeddings, we can measure the degree of similarity and make an informed decision about the signature's authenticity.


# Models Used

**YOLO (You Only Look Once**): Used for real-time signature detection in document images.

**Embedding Extraction Model**: Generates high-dimensional feature vectors (embeddings) from signatures for similarity comparison and authentication.

# Training

## YOLO (Signature Detection)

**Data**: Consists of annotated images containing signatures. Annotations include bounding box coordinates and class labels (signature).
Model

**Model**: YOLO (You Only Look Once) is a convolutional neural network (CNN) designed for real-time object detection. It typically consists of multiple convolutional layers followed by fully connected layers to predict bounding boxes and class probabilities.

**Hyper-parameters**

**No. of Epochs** : 100

**imgsz** : 640

## Embedding Extraction Model

**Data**: Consists of paired images of real and forged signatures for embedding extraction model training. Each pair is annotated with labels indicating authenticity.

**Model**: Typically a deep neural network (e.g., ResNet, MobileNet) adapted for embedding extraction. Pretrained on large datasets, fine-tuned on signature pairs to extract discriminative features.

**Hyper-parameters**


# Evaluation Metrics

## YOLO (Signature Detection)

**Precision** : 0.998

**Recall** : 1.0

**MAP50** : 0.995

**MAP50-95** : 0.983
