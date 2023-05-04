# [DL Model] Image Retrieval with CNN

Here's the table of contents:

TOC
{:toc}

## Prerequsite



## Why?

Implementing Image Retrieval (IR) using CNN seems straight forward. <br/>
With the prior knowledge as Prerequisite, it is doable. <br/>
So here I implemented as a project.

## What is Image Retrieval?

Image Retrieval is, providing we have a **dataset of images**, <br/>
a **target image** we find somewhere else, <br/>
and we want to get **images from the dataset** that are similar to the **target one**.

Tada, Image Retrieval.

## Generally, How Image Retrieval with CNN works?

### What we need?
1. A dataset of images.
2. A CNN model.
3. A target image.

### All we need to do:
1. all the images of the dataset ---> CNN model ---> features of images of dataset
2. the target image              ---> CNN model ---> features of target image
3. compare features of target image to features of images of dataset: <br/>
the shorter the distance is, the more similar the features.
