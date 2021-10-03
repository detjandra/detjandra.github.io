---
layout: default
title: "Research"
permalink: /research/
---

# Highlights of Previous Work



## 1. Hierarchical Survival Analysis

In "A Hierarchical Approach to Multi-Event Survival Analysis" (AAAI, 2021), my co-authors and I approach the task of predicting how the probabiltiy of an individual experiencing multiple events changes over time. More specifically, for each event, we aim to generate a survival curve. A survival curve plots an individual's probability of survival (i.e., not experiencing the event) at various time points in the future, relative to when the prediction was made. However, the task of generating these curves holds many challenges. First, events are often dependent on one another (e.g., given the events of Alzheimer's disease onset and mortality, an individual who is more likely to have Alzheimer's disease onset is also more likely to experience mortality). Second, models that generate survival curves are trained on time-to-event data, where the time at which an individual experiences an event is likely non-deterministic due to noise in the data generating process. While the first challenge has been addressed by previoused work, the second remains under-explored. 

We approach this challenge by breaking the original task (i.e., predicting the probability of survival at each of several time points into the future over some horizon T) into a series of simpler, coarser-grained tasks that eventually build up to the original task. For example, suppose we would like to know the probability of an event occurring at time point 1. Instead of predicting this directly, we could i) predict the probability that the event occurs at time point 1 or time point 2, then ii) predict the probality that the event occurs at time point 1 given that it occurs at time points 1 or 2, and then iii) multiply the results from the previous steps to obtain the final answer. In this case, the coarser-grained task is predicting whether the event occurs at time points 1 or 2, which is more simple than the original task due to its lower variance. For more details, please see the paper.

From a practical standpoint, obtaining accurate survival curves for multiple events (e.g., Alzheimer's disease and mortality) can aid clinicians in deciding the best treatment plan for a patient. Additionally, obtaining accurate survival curves for multiple individuals for a single event can aid clinicians with resource allocation.

This work was done in collaboration with my advisor Jenna Wiens and a (then) undergraduate student I mentored, Yifei He.

## 2. Predicting Alzheimer's Disease from Electronic Health Record Data

In "Cohort discovery and risk stratification for Alzheimer’s disease: an electronic health record‐based approach" (AD-TRCI, 2020), my co-authors and I modeled the risk of developing Alzheimer's disease (AD) using electronic health record (EHR) data. AD is one of the leading causes of death in individuals 65 years and older, and there is currently no way to prevent, stop, or slow the progression of this disease. As a result, predicting which individuals are more likely to develop AD years before symptom onset will be crucial to advancing AD research. However, commonly used sources of longitudinal data, such as those from the Alzheimer's Disease Neuroimaging Initiative (ADNI), do not allow for long prediction horizons, as most participants have fewer than 10 years of followup data. Here, we aimed to use electronic health record data to predict AD onset 10 years in advance.

Our study consists of two parts. In the first part, we developed a cohort discovery tool that labels whether patients in an EHR have AD. Of several cohort discovery tool candidates tested, we found that labeling patients based on ICD billing codes had the highest F1 score. In the second part, we trained a machine learning model to predict whether patients between the ages of 68 and 72 would develop AD within 10 years, where AD onset was labeled based on the cohort discovery tool from the previous part. Overall, we were able to predict AD with modest performance, acheiving an area under the receiver operating characteristic curve (AUROC) of ~0.7. We also found that best performance was achieved when we added more components of EHR data to our model (e.g., predicting based on diagnostic and procedure codes was better than predicting on diagnostic codes alone). Finally, many of the features we identified as important to the model, such as healthcare utilization, aligned with the literature. For more details, please see the paper.

From a practical standpoint, our study shows the potential of EHR data in AD risk prediction. Patients identified as being at a higher risk to develop AD in a routine clinical visit can then be recruited to studies like ADNI or early intervention trials for a more thorough evaluation (e.g., measuring cerebrospinal fluid composition). This is a more cost-effective alternative to conducting a thorough evaluation on all patients above a certain age threshold, as these tests are invasive and expensive. In addition, although we cannot conclude a causal relation between the features identified as important by the model and AD onset, these features can stimulate hypothesis generation for further investigation. 

This work was done in collaboration with two clinicians specializing in AD, Raymond Migrino and Bruno Giordani, and my advisor.

# Current Research

I am currently studying label noise, a different type of noise that can arise in a dataset, in the context of supervised learning. Unlike hierarchical survival analyis, label noise examines the case where some labels in a dataset are incorrectly assigned. This is especially relevant for the Alzheimer's disease study mentioned above. Our labels relied on a cohort discovery tool, which did not have a perfect positive predictive value, Therefore, some individuals who did not convert to AD had the label "converts to AD" in the dataset. Learning in the presence of label noise could further improve our AD risk prediction model.

I am also interested in how EHR time series data can be leveraged to predict AD onset, focusing on blood pressure, and how mild cognitive impairment, a condition that precedes AD, can be identified and modeled from the EHR. 
