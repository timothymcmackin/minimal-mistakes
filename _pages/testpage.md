---
title: Testing multiple galleries on the same page
layout: single
permalink: /testpage
gallery_one:
  - url: /assets/images/3953273590_704e3899d5_m.jpg
    image_path: /assets/images/3953273590_704e3899d5_m.jpg
    alt: "placeholder image 1"
    title: "Image 1 title caption"
  - url: /assets/images/3953273590_704e3899d5_m.jpg
    image_path: /assets/images/3953273590_704e3899d5_m.jpg
    alt: "placeholder image 2"
    title: "Image 2 title caption"
  - url: /assets/images/3953273590_704e3899d5_m.jpg
    image_path: /assets/images/3953273590_704e3899d5_m.jpg
    alt: "placeholder image 3"
    title: "Image 3 title caption"
gallery_two:
  - url: /assets/images/unsplash-image-8.jpg
    image_path: /assets/images/unsplash-image-8.jpg
    alt: "placeholder image 4"
    title: "Image 4 title caption"
  - url: /assets/images/unsplash-image-8.jpg
    image_path: /assets/images/unsplash-image-8.jpg
    alt: "placeholder image 5"
    title: "Image 5 title caption"
  - url: /assets/images/unsplash-image-8.jpg
    image_path: /assets/images/unsplash-image-8.jpg
    alt: "placeholder image 6"
    title: "Image 6 title caption"
  - url: /assets/images/unsplash-image-8.jpg
    image_path: /assets/images/unsplash-image-8.jpg
    alt: "placeholder image 7"
    title: "Image 7 title caption"
---

Hi!

{% include gallery id="gallery_one" caption="Gallery 1" %}

{% include gallery id="gallery_two" caption="Gallery 2" %}