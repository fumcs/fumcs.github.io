---
layout: page
title: Data Augmentation for Fire Detection
description: How to use Style Tranfer for Data Augmentation in a Fire Detection System
img: assets/img/7.jpg
# redirect: https://github.com/mamintoosi/ST-for-DA-in-FD
importance: 3
# category: work
related_publications: ST_for_DA_2022
img: /assets/img/ST_for_DA_2022/day2night-img67.jpg
tags: DL, GAN
categories: Deep-Learning
---

Style Transfer for Data Augmentation in Convolutional Neural Networks Applied to Fire Detection

Adequate training data is essential in all supervised learning methods, including deep learning and machine vision. One of the approaches used to increase the number of training examples in deep learning is the "data augmentation" method. This method involves rotation transformation, transitions, and cropping on training images, which leads to an increase in the number of samples, which are different from training data. In this paper, the "style transfer" algorithm is used to increase the number of training samples. The goal in style transfer is to apply the appearance or visual style of one image to another image. In this paper, this method is used to produce new training examples and as an application, the proposed method is applied to the problem of fire detection. Assuming that the training images recorded during the night are less than the samples taken during the day, by applying a style transfer method, the images of the day are converted into night images and added to the data set as training data. The test results show the efficiency of the proposed data augmentation method. On average, the correct detection rate has increased by 7%.

For more details please see the [Github of the work](https://github.com/mamintoosi/ST-for-DA-in-FD)

Some day light images that transformed to night:
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="https://github.com/mamintoosi/ST-for-DA-in-FD/raw/main/images/day2night/img%20(67).jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/fox.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/3.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

You can also put regular text between your rows of images.
Say you wanted to write a little bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, *bled* for your project, and then... you reveal its glory in the next row of images.


<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>


The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

{% raw %}
```html
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
```
{% endraw %}
