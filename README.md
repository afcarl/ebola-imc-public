# Prognostic models for Ebola virus disease 

This repo holds the Python and R scripts used to generate the prognostic models for Ebola virus disease, derived from the clinical metadata collected by International Medica Corps (IMC) during the 2014-16 Ebola outbreak, and the source code of the proof-of-concept Android and iOS Ebola RISK app that use these models to provide care and managment recommendations based on the clinical features that are most predictive of outcome.

The preprint of the paper describing this work is available on [bioRxiv](http://biorxiv.org/cgi/content/short/294587v3). It is a continuation of a previous paper published on [PLOS Neglected Tropical Diseases](http://journals.plos.org/plosntds/article?id=10.1371/journal.pntd.0004549) in 2016.

# Model fitting and validation

The Logistic Regression models predicting outcome (death/survival) based on available demographic, vitals, sign/symptom and lab variables were trained on the IMC dataset comprising 470 patients from Sierra Leone and Liberia, and then validated on two independent datasets from patients treated at the Kenema Government Hospital and the GOAL-Mathaska care unit in Port Loko district, both in Sierra Leone.

The scripts are organized into several Jupyter notebooks:

1. Bivariate analysis: This notebook contains the code for the bivariate analysis of all the variables in the data against Disposition (outcome).
2. CFR & Age: This notebook plots the graph of case fatality rate (CFR) as function of age
3. CFR & Temp: This notebook plots the graph of temperature as function of age.
4. Model exploration: Contains code to explore redundancy and clusters in different sets of predictors. This notebook informed the construction of the final prognostic models.
5. Min & Full models: Trains the two logistic regression models described in the paper (minimum and full), by pooling several models from multiple imputation with MICE. 
6. Model properties: This notebook evaluates different models and gives the minimum and maximum contribution from each term, which are needed for the Ebola RISK app.
7. Kenema Validation: This notebook validates the IMC models on the Kenema dataset.
8. Figures for paper: The code that generates the final ROC and discrimination plots for the IMC models

# Risk visualization and care recommendation apps

The source code of the Ebola RISK app for the Android and iOS platforms is provided as separate Android Studio and Xcode projects. The app is available on [Google Play](https://play.google.com/store/apps/details?id=org.broadinstitute.ebolarisk) and Apple's [App Store](https://itunes.apple.com/us/app/ebola-risk/id1376937550?mt=8&ign-mpt=uo%3D4).

