# Introduction

The primary objective of this project is to develop a robust system that can automatically detect signatures in documents/cheques and determine their authenticity. By extracting and comparing embeddings, the system can accurately identify whether a given signature is genuine or forged.


# Solution Overview



**Signature Object Detection with YOLO**: We use the YOLO algorithm, known for its efficiency and accuracy, to detect signatures within document and cheque images. YOLO's ability to perform real-time object detection makes it ideal for our application, ensuring quick and reliable signature localization.

**Embedding Extraction**: Once the signatures are detected, the next step involves extracting their embeddings. These embeddings are high-dimensional feature vectors that capture the unique characteristics of each signature.

**Similarity Comparison**: To determine the authenticity of a signature, we compare the embeddings of the detected signatures with those from a reference dataset containing both real and forged signatures. By calculating the cosine similarity between embeddings, we can measure the degree of similarity and make an informed decision about the signature's authenticity.
