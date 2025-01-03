---
title: "Introduction"
permalink: "/intro/"
layout: page
---

## Functional Magnetic Resonance Imaging (fMRI) Data
fMRI is a brain imaging technique that measures and maps brain activity by tracking oxygen consumption. fMRI measures blood-oxygen-level-dependent (BOLD) signals in the brain, based on the theory that active brain areas consume more oxygen than inactive areas. During an experiment, subjects commonly perform a set of tasks in the scanner, while a series of brain images are acquired throughout the course of the experiment. Task-related brain activation is then measured by the BOLD signal changes between these images. 


fMRI data can be thought of as four-dimensional images, consisting of a sequence of three-dimensional brain volumes (spatial element) across a time series (temporal element). Similar to how a digital image is formed by a number of pixels, each brain volume in fMRI is made up of voxels - small, three-dimensional cubes. The spatial resolution of fMRI scans is determined by the size of these voxels, which are commonly 2 mm × 2 mm × 2 mm. At this spatial resolution, a single scan of a whole brain volume contains approximately  778,000 voxels. Each voxel’s position within the brain is represented using x, y, and z coordinates. The temporal resolution of fMRI data is defined by the repetition time (TR)—the time it takes to capture a complete brain volume. TR is usually set to two seconds. 


During an fMRI scan, neural activity is measured across the time series for each voxel. For example, in a 30-minute experiment with a TR of two seconds, a BOLD value is recorded for all 778,000 voxels every two seconds. This process generates 900 whole-brain volumes and approximately 700 million individual BOLD responses. The massive amount of fMRI data makes it very difficult to analyze. To add to the challenge, fMRI data is often noisy in nature, with noise coming from subjects’ head movement during scans, and from the magnet of the fMRI scanner itself. 

## Univariate fMRI Method Using General Linear Model (GLM)
Traditionally, fMRI data is analyzed using a hypothesis-driven univariate analysis to estimate the effect of experimental variables on the activation of brain regions. GLM is applied to the fMRI data from a single voxel at a time, which means that to analyze fMRI data from the whole brain, the GLM will be run about 778,000 times separately. The GLM models the “reference function”, which is the predicted BOLD response pattern throughout the time series if the particular voxel is involved in the task. The similarity between the reference function and the observed BOLD response is then determined by estimating the activation parameter (beta) in the model for each individual voxel. A statistically significant beta value suggests strong task-related activation of the voxel. By repeating this process for all voxels, each is assigned a beta value, allowing researchers to identify clusters of voxels that show strong activation, and thus make inferences about the brain regions that are engaged during the task. 

## A GLM example
Some patients with brain lesions may sometimes develop an impairment in way-finding within the environment, and such impairment was suggested to stem from an impaired ability to perceive and make use of surrounding landmarks, particularly buildings. Aguirre et al. (1998) hypothesized that there is an area in the brain that is specialized for perceiving landmarks, and it would exhibit selective neural response to building stimuli. To test the hypothesis, subjects performed a visual object recognition task during an fMRI scan. They were shown pictures of faces, buildings, and general inanimate objects, and were instructed to memorize them. Later during the testing phase, the pictures were presented along with new pictures, and subjects indicated whether they recognized the pictures using a response button. 


GLM was then applied to the fMRI data to identify voxels that showed task-related activation. To identify the building-sensitive brain area, two t-contrasts were evaluated: “buildings > faces”, which represented voxels with greater activation (higher beta value) when remembering building stimuli than remembering face stimuli, and “building > general objects”, which represented voxels with greater activation when remembering building stimuli than remembering general object stimuli. This technique is known as the neuroimaging double dissociation, which aims to isolate voxels showing specific task-related responses. Voxels with significant t-values at α = 0.05, corrected for multiple comparisons using Bonferroni correction, were retained. Building-sensitive voxels were identified in the occipital cortex (see Figure 1), suggesting that this brain area may play a role in recognizing buildings during navigation. 


#### Figure 1


![Aguirre GLM results](/assets/glmresults.png)

(Aguirre et al., 1998)


## A Problem with Univariate fMRI Analysis
A major limitation of the univariate fMRI method is that it does not take into account spatial correlations among voxels, as it assumes activations in each voxel and its neighboring voxels are independent of each other. However, activations in neighboring voxels are shown to be highly correlated. If one voxel shows high activation, it is likely that high activation will also be observed in its neighboring voxels. 


In neuroscience, a dominant idea is that each behaviour or cognitive function is supported by a *network* of coactivated brain regions. Multivariate fMRI methods are considered to be more suitable for uncovering spatially structured signals that cannot be modeled by GLM, since multivariate methods take into account the relationships between voxels, while univariate methods do not. Furthermore, multivariate methods typically operate simultaneously on activity patterns from all voxels, and consider activation in all voxels in the brain as a single observation, while univariate methods require a separate significance test for each voxel, which leads to increased error rate.

