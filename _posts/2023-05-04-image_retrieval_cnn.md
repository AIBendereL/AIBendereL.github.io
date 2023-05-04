# [DL Model] Image Retrieval with CNN

Table of contents:

1. TOC
{:toc}

## Prerequsite

1. You know what a dataset of images is.
2. You know how CNN works, high-level (basic).

## Why?

Implementing Image Retrieval (IR) using CNN seems straight forward.  
With the prior knowledge in Prerequisite, it is doable.  
So here I implemented IR with CNN as a project.

## What is Image Retrieval?

Image Retrieval is, providing we have a **dataset of images**,  
a **target image** we find somewhere else,  
and we want to get **images from the dataset** that are the most similar to the **target one**.

Tada, Image Retrieval.

## How Image Retrieval with CNN works?

### What is "similarity" between 2 images?

For computer, each image has a way to be encoded, or has a "code" that represent the content of that image.  
An image is usually encoded into a list of numbers. In other words, a "code" is usually a list of numbers.  
So the "similarity" of 2 images will be the difference in the "codes" between 2 images.

### What we need?
1. A dataset of images.
2. A CNN model.
3. A target image.

### All we need to do:
1. all the images of the dataset --(input)--> CNN model --(output)--> list of features of dataset images
2. the target image &emsp; &emsp; &emsp; &emsp; --(input)--> CNN model --(output)--> features
3. compare features of target image to features of images of dataset:  
the shorter the distance is, the more similar the features.
