---
layout: post
title: Few Shot Learning - Siamese Networks 
subtitle: Draft- Pairwise and Triplet
cover-img: /assets/img/path.jpg
thumbnail-img: /assets/img/few_shot_target.jpg
share-img: /assets/img/path.jpg
tags: [few shot learning, siamese networks, pairwise, triplet]
author: Cristi Maldonado
---

Pairwise Siamese Networks are a type of neural network architecture designed for tasks involving similarity or dissimilarity measurement between pairs of inputs. The term "Siamese" refers to the idea that the network has two identical subnetworks, often called twins or branches, which share the same weights and architecture. These subnetworks process individual inputs, and their outputs are then compared to measure the similarity or dissimilarity.

Here's a breakdown of the key components and concepts associated with Pairwise Siamese Networks:

### Architecture

The Siamese network consists of two parallel branches, each processing one of the input samples independently.
Both branches share the same set of weights and are identical in terms of architecture.

### Objective Function 

The primary objective of a Pairwise Siamese Network is to learn a similarity or dissimilarity metric.
The network is trained using pairs of examples, with each pair having a label indicating whether the examples are similar or dissimilar.
The contrastive loss or triplet loss is commonly used as the objective function. These loss functions encourage the network to minimize the distance between similar pairs and maximize the distance between dissimilar pairs.

### Training Data

During training, the network is fed pairs of inputs along with corresponding labels (similar or dissimilar).
The network learns to map input pairs in a way that similar inputs are close in the learned representation space, while dissimilar inputs are far apart.

### Applications

Pairwise Siamese Networks find applications in various domains such as image recognition, facial recognition, signature verification, and text similarity.
In image recognition, for example, the network can be trained to determine if two images contain the same object or not.
Distance Metric:

The learned representation in the Siamese network can be used to calculate a distance metric between input pairs.
Commonly used distance metrics include Euclidean distance or cosine similarity.

### Inference

During inference, the trained Siamese network can be used to compare new pairs of inputs and determine their similarity or dissimilarity based on the learned metric.
Pairwise Siamese Networks have proven to be effective in tasks where the focus is on learning a meaningful similarity metric between pairs of inputs. Their ability to generalize to new, unseen pairs makes them valuable in various applications, particularly in scenarios where labeled data for similarity is limited.