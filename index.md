---
layout: page
title: ""
---


## What are multivariate fMRI methods?
Traditionally, functional magnetic resonance imaging (fMRI) data are analyzed using univariate analyses to estimate the effect of experimental variables on the activation of brain regions. In a whole-brain activation analysis with one million brain voxels for example, the univariate analysis method analyzes one voxel at a time, which means the general linear model (GLM) would be run one million times. This approach assumes that activations in each voxel and its neighboring voxels are independent of each other. However, activations in neighboring voxels are in fact highly correlated. This gave rise to different multivariate methods such as principal component analysis (PCA) and independent component analysis (ICA) for analyzing fMRI data, which consider activation in all voxels in the brain as a single observation, and generally allow for dimension reduction to identify task-related brain activity.


This website introduces two types of multivariate functional magnetic resonance imaging (fMRI) analysis methods: principal component analysis (PCA) and independent component analysis (ICA). The "Introduction" section gives a broad overview of fMRI data and the univariate analysis method. The following sections introduce each multivariate fMRI method. For each method, an example study is included to help illustrate the analysis technique.


