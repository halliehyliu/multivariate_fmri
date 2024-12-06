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

## A PCA Example
Bias against disconfirmatory evidence (BADE) is a form of cognitive bias that is associated with the persistence of delusion in schizophrenia. Patients tend to focus on confirmatory evidence that reinforces delusional beliefs, while struggling to integrate evidence that contradicts them. In a study by Lavigne et. al (2020), the authors aimed to examine the functional networks underlying evidence integration in schizophrenia by applying PCA onto task-fMRI data. Both schizophrenia patients and healthy controls completed an evidence integration task during an fMRI scan. 


fMRI data was analyzed using constrained PCA (CPCA), which is a variation of PCA that performs PCA only on a subset of the overall variance, such that the resulting components reflect specific patterns of interest. In this study, the researchers wished to only perform PCA on task-related variances within the voxel activations, therefore they conducted a multivariate version of GLM to extract only the activity related to evidence integration specifically. PCA was then performed on the resulting data, and a scree plot was examined to determine the number of components to retain. The analysis yielded three task-related components corresponding to known networks involved in evidence integration in healthy adults: visual attention network (VsAN; dorsal anterior cingulate cortex, insula, occipital regions), default-mode network (DMN; precuneus, cingulate cortex, ventromedial prefrontal cortex, occipital regions, parietal cortex), and cognitive evaluation network (CEN; orbitofrontal cortex, inferior frontal gyrus, parietal cortex) (see Figures 4-6). Compared to healthy controls, schizophrenia patients exhibited increased VsAN activation, reduced DMN deactivation, and reduced CEN activation. The authors concluded that aberrant network activations may underlie the cognitive biases in schizophrenia patients. 

#### Figure 4 Component 1 - Visual Attention Network (VsAN)
![Lavigne Component 1](/assets/lavignecomp1.png)


#### Figure 5 Component 2 - Default-Mode Network (DMN)
![Lavigne Component 2](/assets/lavignecomp.png)


#### Figure 6 Component 3 - Cognitive Evaluation Network (CEN)
![Lavigne Component 3](/assets/lavignecomp.png)

