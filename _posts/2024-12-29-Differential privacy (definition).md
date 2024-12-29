---
layout: posts
classes: wide
title: "Differential privacy"
date: 2024-12-29 23:30:00 +0900
categories: [Posts]
tags: [DP]
excerpt: "(1) Definition."
draft: true
---

The differential privacy is a concept suggested by Cynthia Dwork, Frank McSherry, Kobbi Nissim and Adam Smith who won G&ouml;del Prize in 2017 for the contribution. There exists many criteria of the privacy or algorithms that are said to be protecting privacy. However, the differential privacy is superior to those for laying a rigorous foundations for privacy.

Definition. (Differential privacy)
> A randomized mechanism $$M:\mathcal{X}\rightarrow\mathcal{Z}$$ such that
> \begin{equation}\mathbb{P}\left(M(X)\in S\right)\leq e^\epsilon \mathbb{P}\left(M(X')\in S\right)\end{equation}
