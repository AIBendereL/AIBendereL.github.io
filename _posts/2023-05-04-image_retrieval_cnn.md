# [DL Model] Image Retrieval with CNN - Baseline

Table of contents:

1. TOC
{:toc}

## Who this blog is for

This blog is about What Image Retrieval using CNN looks like, in general.  

If you are learning Deep Learning at high-level (basic), and want to apply that to an Image Retrieval system, we are on the same boat and you are at the right place.  

I try to make the blog simple without bulky details, with the hope that it can provide you with a clear view of the system.  
Meanwhile, I have code on Github for experimenting and reproducing if needed.  

## Prerequsite

1. You know what a dataset of images is.
2. You know how CNN works, high-level (basic).

## Why?

Implementing Image Retrieval (IR) using CNN seems straight-forward.  
With only some basic knowledge as Prerequisite, it is doable.  
So here I implement IR with CNN as a project.  

## What is Image Retrieval?

Image Retrieval is, providing we have a **dataset of images**,  
a **target image** we find somewhere else,  
and we want to get **images from the dataset** (i.e: top k images) that are the most ***similar*** to the **target one**.

Boom, Image Retrieval.

### What is ***similarity*** between 2 images?

For Image Retrieval task, each image has a way to be encoded, or has a *code* that represent the content of that image.  
An image is usually encoded into a list of numbers. In other words, a *code* is usually a list of numbers.  
So the ***similarity*** of 2 images will be **the difference in the *codes*** between 2 images.

## How CNN helps with Image Retrieval?

CNN makes Image Retrieval become easier and straight-forward.

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

### How we do
1. All the images of the dataset ----> CNN model ----> **(A) the list of codes** (all the codes of all the images)  
2. The target image &emsp; &emsp; &emsp; &emsp; ----> CNN model ----> **(B) the target image code**  
3. Compare each of the code in **(A) the list of codes** to **(B) the target image code**.  
4. Return top k codes in **(A) the list of codes** that are the least different from **(B) the target image code**.  
5. Return k images corresponding to the top k codes.  

## Experiment

### Setup

The dataset contains 1000 images of 100 species of animals, each species has 10 images.  
For the target image, I picked (for easy demonstration) 3 images of each random species on Google.  

**According to our system**, the result is the top 10 images of the dataset which are the most similar to the target image.  
The order is as follow:  
```
1  2  3  4
5  6  7  8
9  10 T

* 1 is the top 1 image, 10 is the top 10 image.  
* T is the target image.  
``` 

### Result

1. Target image: **a bulbul** (bird).

<img src="/images/result_bulbul.JPG" width= "60%" height= "60%" center= True>

*Top 1 is an image of a bulbul. However, the others are not images of a bulbul*. 

<br/>

2. Target image: **a loggerhead** (turtle).

<img src="/images/result_loggerhead.JPG" width= "60%" height= "60%">

*Top 1 is an image of a loggerhead. However, the others are not images of a loggerhead*.

<br/>

3. Target image: **a whiptail** (lizard).

<img src= "/images/result_whiptail.JPG" width= "60%" height= "60%">

*Top 1 is an image of a whiptail. However, the others are not images of a whiptail*.

## Issue

### What we want

We want our system to return images of the **same species** as the target image.  
We also want our system to return as **many images in top 10** as possible.  
(For our dataset, each species has 10 images, so the max and ideal number of images returned in top 10 is 10)

### What we get

As we can see, although our system is able to retrieve 1 truely similar image, and the image is top 1, it is not close to what we want.  

### How close is our system to what we want?

Actually, I tried some other images and the system returned nothing relevant.  
So literally, it is not even close.  
:bedge:

## Summary

I implement **Image Retrieval with CNN**.  
CNN helps with producing the code in a very **straight-forward** way.  
However, the system's performance needs improvement.  

## Code  

Here is my code for experimenting.  

I suggest to use it as a reference **for the workflow only**.  
Due to the fact that, the system's performance is only at baseline level.  

[*Image Retrieval with CNN code link (Github)*](https://github.com/AIBendereL/Image_Retrieval_with_CNN_baseline/tree/main)

One thing to be mentioned is that, in the Github code,  
I use the word *feature* for *image code*.  
The reason is that, as I mentioned before, we will get the *image code* from the output of one of the lastest layer of CNN, and the output of a layer is called *feature map*.  
Therefore, in general, people will use the word *feature*.  

## Thoughts after I recovered from a headache

After recovering from a headache given by the system performance, I sought for another one by thinking about improvement in the system's performance.  

Apparently, the result is not good. I want a Image Retrieval with CNN system that can retrieve at least 5 images in top 10.  
So I decide to try to improve the system. But it is for another blog (maybe).  

The workflow is kinda straight-forward tho, thanks to CNN.  
This should help improving the system performance to be easy.  

I heard that, a good practice when doing a Deep Learning project, or building Deep Learning system is, first, to build it end-to-end, in other words, to build a baseline.  
Then iterate over it again and again, end-to-end, for incremental improvement.  
So here it is, the baseline with hope.  

## What next?

For system improvement attempts,  
If I manage to improve the system successfully, there will (may)be a blog "IR with CNN Phase 2", or something like that.  
On the other hand, if it is doomed, please visit my other blogs if you are interested.   

<br/>

---------- Thank you for reading ----------
