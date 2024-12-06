---
title: "Principal Component Analysis"
permalink: "/PCA/"
layout: page
---

PCA is a form of multivariate decomposition method that is used to reduce dimensionality in high-dimensional or noisy datasets. In fMRI, PCA is usually used as a preprocessing step to reduce noise and dimensionality, preparing the data for further analysis. PCA identifies main components from the fMRI activation patterns that capture the most variance, and aims to summarize the variability in the data in as few components as possible. It does so by measuring the covariance between all pairs of voxels, identifying key correlations within the activation patterns, and transforming them into orthogonal uncorrelated components (Jolliffe 1986). The first component (or eigenvector) represents the combination of voxels that captures the greatest variance between pairs of voxels, the second component represents the largest source of residual variance orthogonal to the first component, and so on. Each resulting component is represented as a spatial map showing the brain regions involved, with numerical weights specifying how strongly the component is activated on each TR. 


To determine the right number of components in the dataset, especially in the context of noise reduction during fMRI preprocessing, there are a couple of methods that researchers tend to use. First, as task-related activation should show more variability than noise, task-related components should have large eigenvalues, while noise-related components should have small eigenvalues. Researchers may therefore retain only the components accounting for the most variance which collectively account for a desired amount of variance (e.g., 90%). Second, researchers may examine a scree plot of eigenvalues and look for the change in rate by which eigenvalues decrease. Third, researchers may also visually examine the brain map and time series plots of each component to determine whether the neural patterns observed are task- or noise-related. Each component is represented as a spatial map showing the brain regions involved, with the regions being most active shortly after the event to which they are responding (See Figure 2). On the other hand, components related to head movements may show only sporadic activation spikes, and the brain map should display small clusters near the skull (See Figure 3). 


Further, PCA has no free parameters for estimation, as it only involves the orthogonal rotation of the data, and therefore does not require model-fitting. However, PCA assumes multivariate normal distribution of data, which may not be the most ideal for fMRI as data might not necessarily be normally distributed. 

#### Figure 2
![PCA task component example](/assets/pcataskcomp.png)
(Ashby, 2019)

The dotted curve in the bottom panel is the predicted BOLD response to task stimuli.


#### Figure 3
![PCA noise component example](/assets/pcanoisecomp.png)
(Ashby, 2019)


## heading
11234

## A PCA Example
1243234

## References
