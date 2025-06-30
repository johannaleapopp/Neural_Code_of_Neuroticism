# Neural_Code_of_Neuroticism

## 1. Scope 
This repository contains scripts that were used to conduct analyses in **“Neural Code of Neuroticism: New Perspectives through Inter-Subject Representational Similarity Analysis”**, coauthored by Johanna L. Popp, Martin Weiß, Joshua Faskowitz and Kirsten Hilger (doi: will be updated after publication). In brief, we investigated the neurobiological bases of individual differences in neuroticism  (Five-Factor Model; Costa & McCrae, 1992; Goldberg, 1990) by applying Inter-Subject Representational Similarity Analysis (IS-RSA; Finn et al., 2020) to a subsample of participants (N = 184) from the publicly available Human Connectome Project (HCP; Van Essen et al., 2013) for whom fMRI data during naturalistic viewing is accessible (Main study). Our primary goal was to determine whether participants’ similarity in neuroticism (i.e., the tendency to experience negative emotions such as anxiety, irritability or emotional instability) is reflected in the similarity of their brain activity (i.e., brain region-specific activity time courses) during movie watching, as measured with fMRI. Additionally, we sought to determine whether this brain-trait representational similarity is greater during movie scenes that are particularly relevant to neuroticism. To identify such trait-relevant movie scenes, an independent online study with 86 participants was conducted (Pilot study). In case you have questions or trouble with running the scripts, feel free to reach out under [johanna.popp@uni-wuerzburg.de].

## 2. Data
For the Main Study, data from the S1200 sample of the Human Connectome Project funded by the National Institute of Health were used (HCP; Van Essen et al., 2013). Specifically, we used a subsample of participants (N = 184) for which fMRI data during movie watching was available (N = 184). 

For the Pilot Study, we collected data ourselves: Participants (*N* = 86) were recruited through the online platform clickworker (www. clickworker.com) and a PsychoPy experiment was administered online via Pavlovia.

Main Study (HCP): https://www.humanconnectome.org/study/hcp-young-adult/data-releases/
Pilot Study: **Link will be updated after publication**

## 3. Preprocessing
**Needs to be updated --> See Paper**

## 4. Structure and Description of Scripts
### 4.1. Pilot Study
#### 4.1.1. ´Cut_movie_files_HCP´
This script was used to split movie files shown in the HCP (www.humanconnectome.org) into scenes that were rated by the participants in the Pilot Study. 
