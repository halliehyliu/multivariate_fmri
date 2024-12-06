---
title: "Independent Component Analysis"
permalink: "/ICA/"
layout: page
---

ICA on the other hand is a more widely used technique for identifying task-related brain regions and networks. Like PCA, ICA serves to decompose brain activation patterns into spatial components and their associated time courses of activation. The process of determining the number of components to retain is also very similar to PCA. However, while PCA transforms the data to identify main components with maximal variance, the goal of ICA is to separate mixed signals into maximally independent sources, and it does not involve transformation (Bell and Sejnowski, 1995). ICA assumes that observations are linear mixtures of *spatially* independent sources, meaning that it assumes the brain network from one component does not spatially overlap with networks from other components. This way each component is also assumed to be statistically independent from one another, which means that mutual information between components is minimized (i.e. voxel values in any one component do not convey any information about the voxel values in any of the other components). This is in fact a stricter component criteria than the orthogonality (or uncorrelation) criteria in PCA, where brain regions from different components may overlap. As a result, ICA is typically more powerful and sensitive for identifying more nuanced task-related brain networks by “un-mixing” the observed time series.


ICA involves a process known as “blind source separation” to identify components in a way that maximizes spatial independence and nonnormality of components, which is why ICA also assumes that signals and components have nonnormal distributions. The best way to illustrate blind source separation is the “cocktail party problem”. Imagine if there are several people speaking simultaneously in the same room. Since speech signals are independent of each other, ICA can be used to identify each person’s voice. Unlike PCA, ICA involves model-fitting and has free parameters to be estimated from the data. Both the independent components and the weights associated with them are estimated. The weights of each component represent its relative contribution to the overall signal.

#### Figure 7
![PCA vs ICA](/assets/pcaica.png)

(Calhoun and Adali, 2006)

Figure 7 illustrates the difference between PCA and ICA. From the distribution of the mixed signals, PCA (Figure 7b) identifies the orthogonal vectors but does not find independent vectors. In contrast, ICA (Figure 7c) is able to find the independent vectors of the linear mixed signals and is thus able to restore the original sources.

## ICA Example 1: The Effects of Alcohol on Brain Networks
Alcohol is known to depress neural activity and disrupt cognitive-motor processes. Calhoun and colleagues (2004) were interested in how brain networks are affected by alcohol intoxication during simulated driving. During fMRI scans, participants completed a simulated driving task under three conditions: sober, low-dose alcohol, and high-dose alcohol. The task consisted of three events: fixation, active driving, and passively watching a simulated driving scene. Using ICA, the researchers identified 25 brain networks. Upon visual inspection of the brain networks and their corresponding time courses, the researchers determined that seven of them were driving-related brain networks (see Figure 8). A comparison of the activation time courses of these components across conditions revealed that regions in the orbitofrontal cortex and motor cortex were the most affected by alcohol intoxication (the pink and the red components in Figure 8). The study concluded that cognitive-motor impairments resulting from alcohol consumption are mainly modulated through orbitofrontal and motor regions.

#### Figure 8
![Calhoun ICA](/assets/calhounica.png)

(Calhoun et al., 2004)

## ICA Example 2: Comparing PCA and ICA in fMRI Data Analysis
To compare component analysis results on fMRI data between PCA and ICA, McKeown et al. (1998) conducted a study where they used both PCA and ICA on the same dataset. They hypothesized that ICA would be more sensitive in capturing the key task-related activations than PCA. This is because task-related signals account for only a small part of the total variance in fMRI data, therefore using PCA, which captures the greatest variance in the data, may not precisely detect the more fine-grained neural patterns that underlie a certain neural process. 


In this study, a subject underwent an fMRI scan while completing a Stroop color-naming task. The fMRI data was then analyzed using PCA and ICA. To identify the component most closely related to the task in each analysis, the researchers created a reference function that modeled the predicted activation time course of the task, and correlated that with the time course of each of the PCA and ICA components. The PCA component with the highest correlation with the reference function had a coefficient of 0.46, while the ICA component with the highest correlation had a coefficient of 0.92 (See Figure 9). The activity detected by the ICA component was more closely related to the task, and the component captured more activity in the visual areas, which aligned well with prior research findings on Stroop task. The results suggest that ICA is more effective in isolating task-related neural patterns, and is a promising exploratory tool for fMRI data. 

#### Figure 9
![Mckeown](/assets/mckeown.png)

(McKeown et al., 1998)
