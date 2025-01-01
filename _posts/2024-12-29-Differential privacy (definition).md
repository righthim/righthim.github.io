---
layout: posts
classes: wide
title: "Differential privacy"
date: 2024-12-29 23:30:00 +0900
categories: [Posts]
tags: [DP, privacy]
excerpt: "(1) Definition."
draft: true
use_math: true
---

Privacy leakage of machine learning models can be a critical issue in data-driven industries. For example, chatbot that outputs a personal information of an individual used in training. As a result, privacy leakage and methods to prevent them were and are being studied. However, due to the wide range of machine learning applications, the corresponding privacy leakage concerns are also shaped and constraint differently according to the circumstances, resulting into diversed approaches towards privacy-protection in machine learning. As one studying one of such approach, the differential privacy, I will skim through the existing literatures in theory and practice of the privacy-protection in machine learning try to position the differential privacy among them in the following series of posts, in the purpose of self-summary.

Throughout the posts I will call the adversarial attempts to leak private infromation of the training data used in the model as the **privacy attack**. Although private information can be leaked by an accident as in the example of the chatbot, it usually requires some dedicated algorithms. By studying effective privacy attacks, we can find out the weaknesses of models and refine them. Related taxonomy can be found in [A Survey of Privacy Attacks in Machine Learning](https://dl.acm.org/doi/10.1145/3624010) although their terminology includes attacks on model parameter in the privacy attack too.

There are various sorts of privacy attacks according to their goals, prior knowledge, implementations, etc. For instance, membership inference attacks aim to inference whether the given data belongs to the training data whereas reconstruction attacks aim to reconstruct some of the training data. As there are so many of them, it is possible that even if a model is resistant to certain privacy attacks, it can be vulnerable to others. Therefore, one can't help hope for a model guaranteeing the ultimate safety from every possible attacks. Too good to be true but still, the approach called differential privacy is the candidate of achieving it.

How can differential privacy guarantee such? First, one needs to understand that privacy can not be protected 100%.  It requires models give randomized output so that the *distribution* of the random output does not varies significantly according to the individual

Definition. (Differential privacy)
> A randomized algorithm $M:\mathcal{X}\rightarrow\mathcal{P}(\mathcal{Z})$ is $epsilon$-differentially private if
> \begin{equation}\mathbb{P}\left(M(D)\in S\right)\leq e^\epsilon \mathbb{P}\left(M(D^\prime)\in S\right)\end{equation}
> holds for every $D,D^\prime,$ and $S$ where $D$ and $D^\prime$ are datasets that differs by an individual and $S$ is any event.

The differential privacy is a concept suggested by Cynthia Dwork, Frank McSherry, Kobbi Nissim and Adam Smith who won G&ouml;del Prize in 2017 for the contribution. There exists many criteria of the privacy or algorithms that are said to be protecting privacy. However, the differential privacy is superior to those for laying a rigorous foundations for privacy.


The definition of the differential privacy says the given algorithm is private if its output does not varies even if an individual of the dataset is changed. Also, note that 
