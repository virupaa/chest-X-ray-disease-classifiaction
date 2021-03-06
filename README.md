# Chest-X-ray-disease-classification

## Introduction

Examining chest X-ray is one of the most frequent and cost effective medical imaging examination.
Radiologists have to spend time diagnosing chest X-ray images to find any potential lung diseases.
Diagnosing x-rays require careful observation and knowledge of anatomical principles, physiology, and
pathology. Developing automated system for such could make a huge impact to the patients, who don’t
have access to expert radiologists.

In our approach, we applied traditional machine learning techniques in building independent binary
classifier for each of the diseases. We pre-processed image gray scale image by resizing and cropping.
SIFT (Scale-invariant feature transform) computer vision algorithm was applied on pre-processed image to
detect feature descriptors in the image. Visual bag of words is constructed from feature descriptors obtained
from the images.Computed visual bag of words is used as a feature vector for SVM. Each model’s output is binary label.

## Dataset

We have used the open dataset available on [NIH](https://nihcc.app.box.com/v/ChestXray-NIHCC/folder/36938765345) for the training purpose.

## Steps for execution

## Create Folders for each disease separately for classification
```python
python script.py
```

## Train the model by extracting features using SIFT
```python
python train.py -t dataset/train/
```

## Visualizing the results
```bash
python test.py -t dataset/test/ --visualize
```

## Flow of the model
![alt text](https://raw.githubusercontent.com/virupaa/chest-X-ray-disease-classification/master/docs/flow.png)

## Extraction of features using SIFT
![alt text](https://raw.githubusercontent.com/virupaa/chest-X-ray-disease-classification/master/docs/sift.png)

## Results 
![alt text](https://raw.githubusercontent.com/virupaa/chest-X-ray-disease-classification/master/docs/result%201.png)

## Accuracy
The Accuracy of the model for each disease on independent binary classifier was 58-60 precent.

## Reason for choosing this approach
Initially, we started with multi-label classifier by training one-vs-rest with data for all the diseases altogether.
However, performance of multi-label was very poor. Accuracy on train was 25.14 % and on CV was 17.21%. 
Upon investigating we found that it was due to data imbalance, while training multi-label one-vs-rest classifier. Hence, we had to implemented
independent binary classifier for each of the diseases.

