# [DL Model] Image Retrieval with CNN

Table of contents:

1. TOC
{:toc}

## Prerequsite

1. You know what a dataset of images is.
2. You know how CNN works, high-level (basic).

## Why?

Implementing Image Retrieval (IR) using CNN seems straight-forward.  
With the prior knowledge in Prerequisite, it is doable.  
So here I implemented IR with CNN as a project.

## What is Image Retrieval?

Image Retrieval is, providing we have a **dataset of images**,  
a **target image** we find somewhere else,  
and we want to get **images from the dataset** (i.e: top k images) that are the most ***similar*** to the **target one**.

Tada, Image Retrieval.

### What is ***similarity*** between 2 images?

For Image Retrieval task, each image has a way to be encoded, or has a *code* that represent the content of that image.  
An image is usually encoded into a list of numbers. In other words, a *code* is usually a list of numbers.  
So the ***similarity*** of 2 images will be **the difference in the *codes*** between 2 images.

## How CNN helps with Image Retrieval?

CNN makes IR become easy and straight-forward.

When I studied at my university back then, I did a similar IR project, but without CNN.  
The main part is to produce the image *code*.  
To did that, there were quite a lot concepts to be learnt and quite a lot of code to be written.  
So complex that I cannot remember them, or have a severe headache whenever I try to recall them now.

However, that day is gone. Now with CNN, it can produce an image *code* in the most straight-forward way.  
The most straight-forward way:  
1. **Input** an image into CNN.  
2. Get the **output** of CNN. (To be more accurate, we will get the output of one of the lastest layer of CNN)  
3. **Flatten** the output. And that is the *code*.  

## How Image Retrieval with CNN works?

### What we need?
1. A dataset of images.  
2. A CNN model.  
3. A target image.  

### How we do:
1. All the images of the dataset ----> CNN model ----> **(A) the list of codes** (all the codes of all the images)  
2. The target image &emsp; &emsp; &emsp; &emsp; ----> CNN model ----> **(B) the target image code**  
3. Compare each of the code in **(A) the list of codes** to **(B) the target image code**.  
4. Get top k codes in **(A) the list of codes** that are the least different to **(B) the target image code**.  
5. Return those images corresponding to the top k codes.  
