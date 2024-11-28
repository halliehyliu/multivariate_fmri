---
title: "Introduction"
permalink: "/intro/"
layout: page
---

## Functional Magnetic Resonance Imaging (fMRI) Data
fMRI is a brain imaging technique that measures and maps brain activity by tracking oxygen consumption. fMRI measures blood-oxygen-level-dependent (BOLD) signals in the brain, based on the theory that active brain areas consume more oxygen than inactive areas. During an experiment, subjects commonly perform a set of tasks in the scanner, while a series of brain images are acquired throughout the course of the experiment. Task-related brain activation is then measured by the BOLD signal changes between these images. 


fMRI data can be thought of as four-dimensional images, consisting of a sequence of three-dimensional brain volumes (spatial element) across a time series (temporal element). Similar to how a digital image is formed by a number of pixels, each brain volume in fMRI is made up of voxels - small, three-dimensional cubes. The spatial resolution of fMRI scans is determined by the size of these voxels, which are commonly 2 mm × 2 mm × 2 mm. At this spatial resolution, a single scan of a whole brain volume contains approximately  778,000 voxels. Each voxel’s position within the brain is represented using x, y, and z coordinates. The temporal resolution of fMRI data is defined by the repetition time (TR)—the time it takes to capture a complete brain volume. TR is usually set to two seconds. 


The basic unit of time within a time series of an fMRI scan is repetition time (TR), which is the time it takes to obtain a whole-brain volume, and is typically set at two seconds. During an fMRI scan, neural activity is measured across the time series for each voxel. For example, in a 30-minute experiment with a TR of two seconds, a BOLD value is recorded for all 778,000 voxels every two seconds. This process generates 900 whole-brain volumes and approximately 700 million individual BOLD responses. The massive amount of fMRI data makes it very difficult to analyze. To add to the challenge, fMRI data is often noisy in nature, with noise coming from subjects’ head movement during scans, and from the magnet of the fMRI scanner itself. 

## Univariate fMRI Method Using General Linear Model (GLM)
Traditionally, fMRI data is analyzed using univariate analysis to estimate the effect of experimental variables on the activation of brain regions. GLM is applied to the fMRI data from a single voxel at a time, which means that to analyze fMRI data from the whole brain, the GLM will be run about 778,000 times separately. The GLM specifies the predicted BOLD response pattern throughout the time series if the particular voxel is involved in the task. With the observed BOLD response in the voxel as the outcome variable, the activation parameter (beta) in the model can be estimated for each individual voxel. A high beta value suggests strong task-related activation of the voxel. By repeating this process for all voxels, each is assigned a beta value, allowing researchers to identify clusters of voxels that show strong activation, and thus determine the brain regions that are engaged during the task. 

## A GLM example

## A Problem with Univariate fMRI Analysis
One major limitation of the univariate fMRI method is that it does not take into account spatial correlations among voxels, as it assumes activations in each voxel and its neighboring voxels are independent of each other. However, activations in neighboring voxels are shown to be highly correlated. If one voxel shows high activation, it is likely that high activation will also be observed in its neighboring voxels. For this reason, multivariate fMRI methods, such as principal component analysis (PCA) and independent component analysis (ICA), are considered to be more appropriate for analyzing fMRI data. These methods consider activation in all voxels in the brain as a single observation, and allow for dimension reduction to identify task-related brain activity. More importantly, multivariate methods typically operate simultaneously on activity patterns from all voxels.
