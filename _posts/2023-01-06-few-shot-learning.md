---
layout: post
title: Few Shot Learning Intro. 
subtitle: Draft- Approaching Few Shot
cover-img: /assets/img/path.jpg
thumbnail-img: /assets/img/few_shot_target.jpg
share-img: /assets/img/path.jpg
tags: [few shot learning, few, small sample]
author: Cristi Maldonado
---

Few Shot Learning has come riding in on a white horse to conteract the major limiation of large classification models. These architectures can be used for various tasks, but in order for it to accomplish its specific task it needs a large dataset specific enough and fine-tuned to the task at hand. Labelling a large dataset is time-consuming at best and unattainable at worst. Few Shot learning comes in promising to deliver performance with just a few-shot demonstrations. It sounds too good to be true, let's take a looker look at Few-Shot. 

### Few Shot is not a Standard Classification 
The goal with a standard classification problem is to answer this question: "What animal is this? Is this a tiger?" 
If you recall in a standard classification problem you have a large dataset of maybe a 100 classes, including a tiger. You train the model on how to tell those animals apart. Then you show it a tiger, from the test sample, and ask the model "From the classes that you know, is this a tiger?" However, this falls apart when you want to ask the model, "From the classes that you know, is this a vaquita?"; the model never trained on vaquita images. It has no idea what you're asking. It's never trained on a vaquita.  

In contrast, Few-Shot is not asking "Is this a tiger, vaquita, etc.?" Rather you're first showing a small set of samples, support set, and asking "Which animal in the support set is this new animal the most like?" You give them the support set and let the model learn how to figure out which one the animal is closes to. In this way, Few shot is more of similarity excercise and an excercise in meta-learning. 

### What is Meta-Learning?
This is a simple excercise, take a look at the picture below. This is an AI generated never-before-seen creature called poobadeedoo.

![poobadeedo]({{ '/assets/img/few_shot_creature.png' | relative_url }})

Is this also a poobadeedoo? 

![poobadeedo in a store]({{ '/assets/img/few_shot_creature_shot.PNG' | relative_url }})

Most people would say yes this is also a poobadeedoo in a store wearing a shirt. 

This is the idea of meta-learning. You learned how to learn and can now quite quickly tell the similarity of two never before seen creature. The idea of Meta-Learning is particularly important to AI, because it aims to mimic how we are as humans. In the standard classification Neural Networks first randomly initialize some parameters and slowly work our way to the right answer. This is very time consuming and not very human-like. However, as we just demonstrated, we humans we first look for a prior level of understanding (e.g. "I'll check to see if it has eyes." As humans we don't have to be told what eyes are in our existence we learned that and we carry that prior knowledge...) Then we look for the faster way to determine a similarity, (e.g. "Does it have the correct amount of eyes?"). 

### Few Shot Data Sets 

Now let's talk about the data you will be using for your few-shot learning. The support set, training set, and query are essential components in few-shot learning. The training set is the primary dataset used to train the base model. In the example below I'm training with three classes. Normally this will be a very large training data set with many many classes and many examples of those classes. The training set helps the model learn the underlying patterns and features of the task.

![training set]({{ '/assets/img/training_set_few_shot.PNG' | relative_url }}) 

The support set is a subset of the training set and consists of a small number of examples (or support instances) for each class or category.
Each class in the support set has a limited number of instances, providing the model with a glimpse of the specific characteristics of each class.
The support set is used to fine-tune the model or adapt it to recognize new classes during inference. In this small support I have k classes and n examples of that class. 

![support set]({{ '/assets/img/support_set_few_shot.PNG' | relative_url }})

The query set is a set of examples that the model has not seen during training.
It is used to evaluate the generalization performance of the model.The model is tested on the query set to assess its ability to recognize and classify new instances or classes based on the few examples provided in the support set. With this query I will be asking, "Which animal in the support set is this new animal the most like?" 

![query]({{ '/assets/img/query_few_shot.PNG' | relative_url }})

To summarize few-shot learning involves training a model on a small training set with a support set containing a limited number of examples for each class. The model's performance is then evaluated on a separate query set to test its ability to generalize to new, unseen instances. This paradigm is particularly useful in scenarios where obtaining a large amount of labeled data for training is challenging. 

In the next blog we will take a look at Siamese Networks to accomplish few-shot learning. 
