---
weight: 1
title: "Oxford QI"
date: 2015-09-01
lastmod: 2022-08-21 12:26:21
draft: false
author: "Luka Skoric"
images: []

tags: ["projects",]
categories: ["projects"]

featuredImage: "boltzmann_machine.png"
featuredImagePreview: "boltzmann_machine.png"

lightgallery: true
fontawesome: true

toc:
  enable: false
  auto: false
code:
  copy: true
  maxShownLines: 50
math:
  enable: false
  # ...
mapbox:
  # ...
share:
  enable: false
  # ...
comment:
  enable: false
---


I spent the summer of 2015 doing a research internship in Oxford with [Simon Benjamin's group](https://qtechtheory.org/) under [Dr Stefan Zohren](https://scholar.google.co.uk/citations?hl=en&user=mtNQD-8AAAAJ&view_op=list_works&sortby=pubdate). I learned about and worked on projects in quantum and classical machine learning and optimization. I programmed neural networks and implemented optimization algorithms to test theoretical predictions.

The first part of my project was investigating the potential of quantum computers for deep learning, trying to understand and improve on the recent paper by [Microsoft Research](https://arxiv.org/abs/1412.3489) [1]. In the second part, I shifted focus on classical machine learning where I programmed neural networks and compared optimization algorithm (particularly saddle-free Newton method) to support my supervisor's mathematical proofs. More precisely (and perhaps less clearly), I was looking into the eigenvalue distribution of the Hessian matrix in large neural networks and its relation to the Krylov subspace. For more details, the notes from my project can be found below.

Here I first came in touch with deep learning, completing Andrew Ng's Machine learning course on [Coursera](https://www.coursera.org/) to prepare for it. This has served as a basis for my later work in data science and machine learning.

[[1]](https://arxiv.org/abs/1412.3489) N. Wiebe, A. Kapoor, K. M. Svore, arXiv:1412.3489 [quant-ph] (2015)

[{{<rawhtml>}}<i class="fa-solid fa-file"></i>{{</rawhtml>}} Download notes](oxford_notes.pdf)
