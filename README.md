# Voice Research Project: GRBAS Prediction

This repo contains the code for the GRBAS Prediction in Voice Research Lab in HKU.

In this repository, you will find the code to replicate our experiments.
We do not include the datasets used in the research as they are publicly available: [SVD](https://stimmdb.coli.uni-saarland.de/) and [AVFAD](https://acsa.web.ua.pt/AVFAD.htm).
Our internal CSL dataset is not publicly available.

## Introduction

Voice disorders are pathologies that significantly impact patients' quality of life. Preliminary screening for voice disorders is essential; however, the inter-rater and intra-rater reliability of GRBAS assessments by speech therapists is notably low, leading to inconsistencies in voice quality evaluation. This repository proposes a solution aimed at providing objective, effective, and efficient preliminary screening for voice disorders.

## Datasets

We utilized two publicly available datasets: the German SVD and the Portuguese AVFAD. Additionally, we assess the performance of our approach on an internal Hong Kong CSL dataset. Currently, we are using "<a>" sustained vowels with normal pitch as our training data. We refined the datasets to focus on consistent recordings and performed minimal preprocessing, such as cropping to reduce silent segments. Only training data with a sampling rate greater than 44.1 kHz was included.

SVD. The Saarbrücken Voice Database consists of voice recordings and electroglottography (EGG) data, featuring 13 files per recording session. This includes recordings of vowels /a, i, u/ with various pitch variations (normal, high, low, rising-falling) as well as a sentence reading task.

AVFAD. The Advanced Voice Function Assessment Database collects audio recordings of participants performing various vocal tasks, including sustaining vowels /a, e, o/, reading six sentences, reciting a phonetically balanced text, and engaging in spontaneous speech, with each task repeated three times. For consistency, we cropped the audio files into three segments, thus obtaining three audio files for each patient.

We invited six therapists from Hong Kong and four HKU students to assess the GRBAS ratings for each audio sample, providing scores for each of the five components (Grade, Roughness, Breathiness, Asthenia, Strain) on a scale from 0 to 3 (0: Normal, 1: Mild, 2: Moderate, 3: Severe).

The combined ratings from therapists and students were considered, and only those ratings that met a 70% consensus threshold were included in our training dataset.

We extracted acoustic features from the audio files to obtain a tabular dataset with a ordinal target. 

## Training Procedure

We treated this problem as a multiclass classification problem. Traditional machine learning algorithms are used, including Decision Tree, Random Forest, LightGBM, CatBoost and XGBoost. We performed a 10-fold cross validation (CV) for the dataset. We used the default configurations. Experiments were run on a machine equipped with an Intel Xeon CPU with four cores.

## License

This repository is not open source. The code and models provided are for research purposes only. Please reach out for inquiries regarding usage or collaboration.

## Contact

Please contact [Ko Chun Him](chkoad@connect.ust.hk) for any enquiries.
