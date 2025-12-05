---
layout: single
title: "End-to-End Image Classification with Amazon SageMaker"
description: "Hands-on image classification project using Amazon SageMaker."
permalink: /amazon-sagemaker/overview/
classes: wide            
sidebar:
  nav: amazon-sagemaker   
author_profile: false
toc: true
toc_sticky: true

---

## 1. Overview

In this project, I explored how to build, train, and deploy a machine learning model using **Amazon SageMaker**. The goal was to classify images using **Transfer Learning**, a technique that leverages a pre-trained model (ResNet) to solve a new problem with less data and computing time.

This workflow demonstrates how cloud infrastructure can democratize access to powerful AI tools, allowing developers to focus on the application logic rather than the underlying hardware.

## 2. Architecture & Prerequisites

**The Workflow:**

1.  **Storage:** Store training and validation images in **Amazon S3**.
2.  **Training:** Use a SageMaker Notebook Instance to launch a training job.
3.  **Model:** Use the built-in SageMaker Image Classification algorithm.
4.  **Deployment:** Deploy the model to a real-time HTTPS endpoint.

**Prerequisites:**

  * AWS Account with permissions to access S3 and SageMaker.
  * An active SageMaker Notebook Instance.

-----

## 3. Environment Setup

First, we set up the environment by importing the necessary libraries and defining the IAM role that allows SageMaker to access our S3 bucket.

```python
import sagemaker
from sagemaker import get_execution_role
import boto3

# Initialize the session and role
session = sagemaker.Session()
role = get_execution_role()
bucket = session.default_bucket()

print(f"Using S3 Bucket: {bucket}")
print(f"Execution Role: {role}")
```

-----

## 4. Preparing the Data

SageMaker requires data to be in specific formats. For the Image Classification algorithm, we can use the **RecordIO** format or raw images. For this project, I used raw images organized into S3 prefixes.

The specific algorithm image URI is retrieved dynamically based on the region.

```python
from sagemaker import image_uris

# Retrieve the training image for the Image Classification algorithm
training_image = image_uris.retrieve(
    region=session.boto_region_name, 
    framework='image-classification', 
    version='latest'
)

print(f"Training image URI: {training_image}")
```

-----

## 5. Configuring the Model (Hyperparameters)

I configured the `Estimator` object, which orchestrates the infrastructure. I chose a **ResNet-50** architecture and enabled **Transfer Learning** to speed up the process.

**Key Configuration Details:**

  * **Instance Type:** `ml.p2.xlarge` (GPU-accelerated for faster image processing).
  * **Epochs:** 10 (Number of passes through the dataset).
  * **Classes:** 2 (Binary classification for this demo).

<!-- end list -->

```python
# Create the Estimator
image_classifier = sagemaker.estimator.Estimator(
    image_uri=training_image,
    role=role,
    instance_count=1,
    instance_type='ml.p2.xlarge',
    output_path=f's3://{bucket}/output',
    sagemaker_session=session
)

# Set Hyperparameters
image_classifier.set_hyperparameters(
    num_layers=50,               # Using ResNet-50
    use_pretrained_model=1,      # Enable Transfer Learning
    image_shape="3,224,224",     # Channels, Height, Width
    num_classes=2,               # Example: 'Dog' vs 'Cat'
    mini_batch_size=32,
    epochs=10
)
```

-----

## 6. Training the Model

With the configuration set, I initiated the training job. SageMaker automatically provisions the EC2 instances, downloads the container image, pulls the data from S3, trains the model, and tears down the infrastructure when finished.

```python
# Define data channels
train_data = sagemaker.inputs.TrainingInput(
    f's3://{bucket}/train', 
    content_type='application/x-image'
)
validation_data = sagemaker.inputs.TrainingInput(
    f's3://{bucket}/validation', 
    content_type='application/x-image'
)

# Launch training
image_classifier.fit({'train': train_data, 'validation': validation_data})
```

-----

## 7. Deployment & Inference

Once the model training was complete, I deployed it to a persistent endpoint. This creates a REST API that applications can invoke to get real-time predictions.

```python
# Deploy the model to an endpoint
predictor = image_classifier.deploy(
    initial_instance_count=1,
    instance_type='ml.m4.xlarge'
)

print("Endpoint deployed successfully.")
```

**Testing the Prediction:**
To validate the model, I sent a test image payload to the endpoint.

```python
import json
import numpy as np

# Load a test image
with open('test_image.jpg', 'rb') as f:
    payload = f.read()

# Invoke endpoint
response = predictor.predict(payload, initial_args={'ContentType': 'application/x-image'})
result = json.loads(response)

# Output the probability
print(f"Probability scores: {result}")
```

-----

## 8. Cleanup

Cost management is a critical part of cloud architecture. To avoid incurring charges for idle resources, I deleted the endpoint immediately after testing.

```python
predictor.delete_endpoint()
print("Endpoint deleted.")
```

-----

## 9. Conclusion

This project highlighted the power of **SageMaker's managed services**. By handling the heavy lifting of infrastructure provisioning and container management, SageMaker allowed me to focus on the data and the model parameters.

**Key Learnings:**

  * **Infrastructure as Code:** Controlling ML infrastructure via Python SDKs.
  * **Transfer Learning:** Utilizing pre-trained networks to reduce training time.
  * **Lifecycle Management:** Managing the full flow from S3 ingestion to API deployment.
