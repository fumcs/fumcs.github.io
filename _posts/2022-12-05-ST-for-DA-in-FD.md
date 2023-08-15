---
layout: page
title: Data Augmentation for Fire Detection
description: How to use Style Tranfer for Data Augmentation in a Fire Detection System
img: assets/img/7.jpg
# redirect: https://github.com/mamintoosi/ST-for-DA-in-FD
importance: 3
category: research
related_publications: ST_for_DA_2022
img: /assets/img/ST_for_DA_2022/day2night-img67.jpg
date: 2022-11-05
tags: DL, GAN
---

Style transfer is a technique that allows you to change the appearance of an image by applying the style of another image. For example, you can make a photo look like a painting by transferring the style of a famous artist. Style transfer is usually done by using neural networks or deep learning, which can learn the features and patterns of different images and blend them together. Style transfer can be used for various purposes, such as creating digital art, enhancing photos, or generating new images.
The following image show an instance of style transfer. Other instances could be accesible from [our repository](https://github.com/mamintoosi/MMM-Artistic-photoes).

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/ST_for_DA_2022/fox2_feathers.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Unleashing the power of style transfer to enhance fire detection is done  and published in a paper entitled by "Style Transfer for Data Augmentation in Convolutional Neural Networks Applied to Fire Detection".

Abstract:

 In realm of deep learning, the availability of robust training data is paramount. To overcome the scarcity of training samples, we delve into the realm of "data augmentation" techniques. Within this study, we harness the transformative capabilities of the "style transfer" algorithm, which enables the transfer of visual styles from daytime to nighttime images. By leveraging this approach, we augment our training dataset for fire detection, where nighttime samples are limited. The experimental results demonstrate a notable 7% increase in the correct detection rate, affirming the efficacy of our data augmentation method. For comprehensive insights, please consult the corresponding [Github repository](https://github.com/mamintoosi/ST-for-DA-in-FD).

Some daytime images that transfered to nighttime using a night image (middle):
<table  align="center" border="1">
<tr><td> <img src="assets/img/ST_for_DA_2022/img (31).jpg" width="700"> </td></tr>
<tr><td> <img src="assets/img/ST_for_DA_2022/img (35).jpg" width="700"> </td></tr>
</table>
