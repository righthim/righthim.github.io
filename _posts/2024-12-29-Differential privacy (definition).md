---
layout: posts
classes: wide
title: "Differential privacy"
date: 2024-12-29 23:30:00 +0900
categories: [Posts]
tags: [DP]
excerpt: "(1) Definition."
draft: true
use_math: true
---

The differential privacy is a concept suggested by Cynthia Dwork, Frank McSherry, Kobbi Nissim and Adam Smith who won G&ouml;del Prize in 2017 for the contribution. There exists many criteria of the privacy or algorithms that are said to be protecting privacy. However, the differential privacy is superior to those for laying a rigorous foundations for privacy.

Definition. (Differential privacy)
> A randomized algorithm $M:\mathcal{X}\rightarrow\mathcal{P}(\mathcal{Z})$ is $epsilon$-differentially private if
> \begin{equation}\mathbb{P}\left(M(D)\in S\right)\leq e^\epsilon \mathbb{P}\left(M(D^\prime)\in S\right)\end{equation}
> holds for every $D,D^\prime,$ and $S$ where $D$ and $D^\prime$ are datasets that differs by an individual and $S$ is any event.

The definition of the differential privacy says the given algorithm is private if its output does not varies even if an individual of the dataset is changed. Also, note that 
