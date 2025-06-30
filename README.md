# Neural_Code_of_Neuroticism

## 1. Scope 
This repository contains scripts that were used to conduct analyses in **“Neural Code of Neuroticism: New Perspectives through Inter-Subject Representational Similarity Analysis”**, coauthored by Johanna L. Popp, Martin Weiß, Joshua Faskowitz and Kirsten Hilger (doi: will be updated after publication). In brief, we investigated the neurobiological bases of 
individual differences in neuroticism  (Five-Factor Model; Costa & McCrae, 1992; Goldberg, 1990) by applying Inter-Subject Representational Similarity Analysis (IS-RSA; Finn et al., 2020) to a subsample of participants (N = 184) from the publicly available Human Connectome Project (HCP; Van Essen et al., 2013) for whom fMRI data during naturalistic viewing is
accessible (Main study). Our primary goal was to determine whether participants’ similarity in neuroticism (i.e., the tendency to experience negative emotions such as anxiety, irritability or emotional instability) is reflected in the similarity of their brain activity (i.e., brain region-specific activity time courses) during movie watching, as measured with fMRI.
Additionally, we sought to determine whether this brain-trait representational similarity is greater during movie scenes that are particularly relevant to neuroticism. To identify such trait-relevant movie scenes, an independent online study with 86 participants was conducted (Pilot study). In case you have questions or trouble with running the scripts, feel free
to reach out under [johanna.popp@uni-wuerzburg.de].

## 2. Data
For the Main Study, data from the S1200 sample of the Human Connectome Project funded by the National Institute of Health were used (HCP; Van Essen et al., 2013). Specifically, we used a subsample of participants (N = 184) for which fMRI data during movie watching was available (N = 184). 

For the Pilot Study, we collected data ourselves: Participants (*N* = 86) were recruited through the online platform clickworker (www. clickworker.com) and a PsychoPy experiment was administered online via Pavlovia.

Main Study (HCP): https://www.humanconnectome.org/study/hcp-young-adult/data-releases/
Pilot Study: **Link will be updated after publication**

## 3. Preprocessing
**Needs to be updated --> See Paper**

## 4. Structure and Description of Scripts

### 4.1. Pilot Study

#### 4.1.1. `Cut_movie_files_HCP`
This script was used to split movie files shown in the HCP (www.humanconnectome.org) into scenes that were rated by the participants in the Pilot Study. 

#### 4.1.2. `PsychoPy_Experiment[Folder]`
This folder contains the PsychoPy Script all required files used to implement the Pilot Study, where participants rated movie scenes based on their potential to evoke emotions related to neuroticism. A detailed description of the procedure can be found in the methods section of the paper.

#### 4.1.3. `Define_trait_ir_relevant_scenes_clickworker_run_1`
This script was used to analyze the data from Group 1 (rated Movie 1 and Movie 2) that was collected through the online study: The first part includes  a) Import of files that were generated as output from Pavlovia.org b) generation of  scene scores from participants' scene ratings c) computation of neuroticism scores from NEO-FFI responses d) extraction of
demographic data and d) compilation of all relevant information into one csv file. The second part includes a) the analysis of sample characteristics (age, gender, and neuroticism scores) and the identification of trait-relevant and trait-irrelevant scenes, along with the generation of the corresponding plots shown in the Supplementary Material.

#### 4.1.4. `Define_trait_ir_relevant_scenes_clickworker_run_2`
This script was used to analyze the data from Group 2 (rated Movie 3 and Movie 4) that was collected through the online study: The first part includes  a) Import of files that were generated as output from Pavlovia.org b) generation of  scene scores from participant’s scene ratings c) computation of neuroticism scores from NEO-FFI responses d) extraction of
demographic data and d) compilation of all relevant information into one csv file. The second part includes a) the analysis of sample characteristics (age, gender, and neuroticism scores) and the identification of trait-relevant and trait-irrelevant scenes, along with the generation of the corresponding plots shown in the Supplementary Material.

#### 4.1.5. `Repeated_measures_ANOVA_scene_ratings`
This script was used to test (post hoc) with one-way repeated measures ANOVAs whether there are significant differences in scene ratings (i.e., mean scene scores) between trait-relevant and trait-irrelevant scenes. The first part assesses ratings from Group 1 (Movies 1 and 2), while the second part assesses ratings from Group 2 (Movies 3 and 4). 

### 4.2. Main Study
Please note that scripts used to perform the Inter-Subject Representational Similarity Analysis were developed based on a tutorial by Finn & Chang (2021) which can be found here: [Inter-subject Representational Similarity Analysis — Naturalistic Data Analysis](https://naturalistic-data.org/content/Intersubject_RSA.html).

#### Main Sample

#### 4.2.1. `Preparation_behavioral_data_HCP`
This script was used to a) read in behavioral data from the HCP, b) exclude subjects with missing data, c) split the sample into a main and a replication sample and d) analyze demographic data and neuroticism scores. Please note that the assessment of normality of neuroticism distributions was computed in the script: Plots_distribution_neuroticism_scores.

#### 4.2.2. `Motion_exclusion_HCP`
This script was used to identify subjects with excessive head motion under the lenient exclusion criteria (mean framewise displacement (mFD) > 0.55mm) suggested by Parkes et al. (2018).

#### 4.2.3. `Plotting – Assignment of Nodes to Yeo 7 or Yeo 17 networks[**Folder**]`
This script `Match_nodes_to_network`  was used to solve a problem when plotting results in in the IS-RSA Analysis: The data we received from preprocessing are in the order of the Yeo 17 parcellation, but that differs from the Yeo 7 parcellation. However, I need the Yeo 7 parcellation for the node-to-network assignment. Here it was figured out, which node name
from the Yeo 7 parcellation (or index) belongs to the Yeo 17 parcellation. The corresponding excel files (output and input) can also be found in this folder. 

#### 4.2.4. `IS_RSA_analysis_all_scenes`
This script was used to perform the IS-RSA analysis with data from all movie scenes in the main sample. It includes a) installation of the relevant software and packages, b) conversion of the fMRI data c) trimming of time courses, d) assessment of brain similarity, e) assessment of trait similarity and f) computation of brain-trait representational similarity on
whole-brain, network- and region-specific level. 

#### 4.2.5. `IS_RSA_analysis_TR_scenes`
This script was used to perform the IS-RSA analysis with data from all trait-relevant scenes in the main sample. It includes a) installation of the relevant software and packages, b) conversion of the fMRI data c) trimming of time courses, d) assessment of brain similarity, e) assessment of trait similarity and f) computation of brain-trait representational
similarity on whole-brain, network- and region-specific level.

#### 4.2.6. `IS_RSA_analysis_TIR_scenes`
This script was used to perform the IS-RSA analysis with data from all trait-irrelevant scenes in the replication sample. It includes a) installation of the relevant software and packages, b) conversion of the fMRI data c) trimming of time courses, d) assessment of brain similarity, e) assessment of trait similarity and f) computation of brain-trait
representational similarity on whole-brain, network- and region-specific level.

#### 4.2.7. `Perform_t_tests_between_IS_RSA_values_TR_vs_TIR`
This script was used to test whether brain-trait representational similarity is significantly different between trait-relevant and trait-irrelevant scenes in the main sample.

#### Replication Sample

#### 4.2.8. `IS_RSA_analysis_all_scenes_replication`
This script was used to perform the IS-RSA analysis with data from all movie scenes in the replication sample. It includes a) installation of the relevant software and packages, b) trimming of timecourses, c) assessment of brain similarity, d) assessment of trait similarity and e) computation of brain-trait representational similarity on whole-brain, network-
and region-specific level.

#### 4.2.9. `IS_RSA_analysis_TR_scenes_replication`
This script was used to perform the IS-RSA analysis with data from all trait-relevant scenes in the replication sample. It includes a) installation of the relevant software and packages, b) trimming of time courses, c) assessment of brain similarity, d) assessment of trait similarity and e) computation of brain-trait representational similarity on whole-brain,
network- and region-specific level. 

#### 4.2.10. `IS_RSA_analysis_TIR_scenes_replication`
This script was used to perform the IS-RSA analysis with data from all trait-irrelevant scenes in the replication sample. It includes a) installation of the relevant software and packages, b) trimming of time courses, c) assessment of brain similarity, d) assessment of trait similarity and e) computation of brain-trait representational similarity on whole-brain,
network- and region-specific level.

#### 4.2.11. `Perform_t_tests_between_IS_RSA_values_TR_vs_TIR_replication`
This script was used to test whether brain-trait representational similarity is significantly different between trait-relevant and trait-irrelevant scenes in the replication sample.

### 4.3. Post Hoc Analysis 

#### 4.3.1. `Comparison_IS_RSA_values_main_vs_replication_sample`
This script was used to assess the correspondence of region-specific IS-RSA values between 	the main and the replication sample (Scatterplot and Pearson correlation). 

### 4.4. Plots

#### 4.4.1. `Plots_distribution_neuroticism_scores`
This script was used to plot the distribution of neuroticism scores in the Main Study for the main and the replication sample with an updated x-axis range. It was also used to test these distributions for their normality with a Shapiro-Wilk test. 

#### 4.4.2. `Random_distribution_IS_RSA_values_paper_figure`
This script was used to plot a random distribution of IS-RSA values for the figure in the paper that illustrates the study procedure. 

#### 4.4.3. `Parcellation_Yeo_networks`
This script was used to create the figure in the Supplement that illustrates the seven Yeo networks.

## 5. Software Requirements
+ Python version 3.10.14
+ via JupyterNotebook


## References
References
Costa, P. T., & McCrae, R. R. (1992). Normal personality assessment in clinical practice: The NEO Personality Inventory. Psychological Assessment, 4, 5–13. https://doi.org/10.1037/1040-3590.4.1.5

Finn, E. S., Glerean, E., Khojandi, A. Y., Nielson, D., Molfese, P. J., Handwerker, D. A., & Bandettini, P. A. (2020). Idiosynchrony: From shared responses to individual differences during naturalistic neuroimaging. NeuroImage, 215, 116828. https://doi.org/10.1016/j.neuroimage.2020.116828

Goldberg, L. R. (1990). An alternative „description of personality“: The big-five factor structure. Journal of Personality and Social Psychology, 59(6), 1216–1229. https://doi.org/10.1037//0022-3514.59.6.1216

Parkes, L., Fulcher, B., Yücel, M., & Fornito, A. (2018). An evaluation of the efficacy, reliability, and sensitivity of motion correction strategies for resting-state functional MRI. NeuroImage, 171, 415–436. https://doi.org/10.1016/j.neuroimage.2017.12.073

Van Essen, D. C., Smith, S. M., Barch, D. M., Behrens, T. E. J., Yacoub, E., & Ugurbil, K. (2013). The WU-Minn Human Connectome Project: An Overview. NeuroImage, 80, 62–79. https://doi.org/10.1016/j.neuroimage.2013.05.041

## Copyright 
Copyright (cc) 2025 by Johanna L. Popp 

<a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" /></a><br />

Files of Neural_Code_of_Neuroticism by Johanna L. Popp are licensed under <a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/">Creative Commons Attribution-NonCommercial 4.0 International License</a>.
