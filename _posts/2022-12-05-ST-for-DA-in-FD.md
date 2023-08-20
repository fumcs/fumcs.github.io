---
layout: page
title: Data Augmentation for Fire Detection
description: How to use Style Tranfer for Data Augmentation in a Fire Detection System
importance: 3
category: research
related_publications: ST_for_DA_2022
img: /assets/img/ST_for_DA_2022/day2night-img67.jpg
date: 2022-12-05
tags: DL, GAN
featured: true
thumbnail: assets/img/CV.jpg
authors:
  - name: M. Amintoosi
    url: "https://mamintoosi.github.io/"
    affiliations:
      name: FUM, CS Faculty

---

Style transfer is a technique that allows you to change the appearance of an image by applying the style of another image. For example, you can make a photo look like a painting by transferring the style of a famous artist. Style transfer is usually done by using neural networks or deep learning, which can learn the features and patterns of different images and blend them together. Style transfer can be used for various purposes, such as creating digital art, enhancing photos, or generating new images.
The following image show an instance of style transfer. Other instances could be accesible from [our repository](https://github.com/mamintoosi/MMM-Artistic-photoes).

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/ST_for_DA_2022/fox2_feathers.jpg" title="Style Transfer" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
Unleashing the power of style transfer to enhance fire detection is done  and published in a paper entitled by "Style Transfer for Data Augmentation in Convolutional Neural Networks Applied to Fire Detection". The Style of the lower left image is transfered to upper left image.
</div>

Paper Abstract:

 In realm of deep learning, the availability of robust training data is paramount. To overcome the scarcity of training samples, we delve into the realm of "data augmentation" techniques. Within this study, we harness the transformative capabilities of the "style transfer" algorithm, which enables the transfer of visual styles from daytime to nighttime images. By leveraging this approach, we augment our training dataset for fire detection, where nighttime samples are limited. The experimental results demonstrate a notable 7% increase in the correct detection rate, affirming the efficacy of our data augmentation method. For comprehensive insights, please consult the corresponding [Github repository](https://github.com/mamintoosi/ST-for-DA-in-FD).


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/ST_for_DA_2022/img31.jpg" title="Style Transfer" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/ST_for_DA_2022/img35.jpg" title="Style Transfer" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
Some daytime images that transfered to nighttime using a night image (middle).
</div>

