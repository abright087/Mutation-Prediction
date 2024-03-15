# Mutation Prediction Design Doc 
Group project for COMP 383/483 - mutation prediction for viral proteomes with Dr. Whelton Miller. 
## Overview
Viruses mutate extremely frequently, their mutation rate being higher than any other organism. Their ability to quickly evolve has lead to efficient infection of their host, evading antiviral drugs. Due to this characteristic, it has proven difficult to hault the spread of a virus, as seen with the spread of Sars-CoV-2. There is an urgent demand for the accurate predictive tools for viral mutations in order to get ahead of the virus and stop the spread prior to mutation. A previous group has worked with Dr. Miller to create a machine learning model for mutation prediction based on hidden mutation patterns. However, the current model is only fit for the Sars-CoV-2 virus. We aim to expand this model to fit other viruses; Human Papillomavirus (HPV) and Epstein-Barr virus (EBV).

The current machine learning model was trained using the Sars-CoV-2 receptor binding domain. The tool extracts viral genomic sequences from NCBI and preprocesses the sequences to remove non-standard amino acids. The model uses a neural network with long short-term memory, convolutional neural network, and variational autoencoder to return mutational predicions with minimized loss function. To train the model, dimensionality was reduced, 4137 samples of Sars-CoV-2 variants were used in the training dataset, and hyperparameters were optimized. The performance of the model was evaluated in encoder dataframes. The mean-squared error and referencing predicted mutations with current literature were also used to evalute the model.

To expand the toolkit to be applicable for different viruses, we will begin by testing the current tool and evaluting the accuracy of mutation predicition for HPV and EBV. To retrain the model for these viruses, we will use incremental learning techniques with small batches of data, including a new training dataset with HPV and EBV variants. We can achieve this with scikit-learn via the partial_fit method. We will evalute the accuracy of the updated model, ensuring the mutation predicition is accurate for Sars-CoV-2, HPV, and EBV. Lastly, we will compile a summary of our project into a graphical output similar to a poster. If time allows, we will also revise the tool to make it more user friendly by reducing the lines of code necessary to use the tool. The development of this tool will allow for a proactive approach when designing theraputic approaches for viruses.

## Context

- [ ] Estimating the rate of evolution of viral proteomes using a machine learning approach will allow for the 

## Goals & Non-Goals
Our main goal is to further develop a prediction mutation tool for viral proteomes by expanding the pre-existing model, which focuses only on the Sars-Cov-2 virus, to be generalized to more viruses, such as HPV and EBV. 
- Goals
  - Overall goal: adjust the current model to be applicable for various viruses by training the model with new proteomes and adjusting the parameters to improve accuracy
  - Obtain the mutations that are most likely biologically significant
  - Make the current tool more user-friendly
 
- Non-Goals
  - We will not focus on the quantity of mutation predictions returned, but rather the quality / accuracy of the predictions
  - We will not retrain the model from scratch since we want to build upon the pre-existing model, not create a new one
## Proposed Solution

## Milestones
| Week | Hannah Serio | Bright Asante | Mariam Ahmed | James Damaso |
| --- | --- | --- | --- | --- |
| March 11 | Develop design doc, prepare presentation, get current model running | Develop design doc, prepare presentation, get current model running | Prepare presentation, get current model running | Prepare presentation, get current model running |
| March 18 | Run the current model with HPV virus, begin building training dataset with HPV, finalize presentation | Run the current model with EBV virus, begin building training dataset with EBV, finalize presentation | Create scikit-learn partial-fit pipeline | Create scikit-learn partial-fit pipeline |
| March 25 | Develop retraining pipeline and run training datasets | Develop retraining pipeline and run training datasets | Develop retraining pipeline and apply training datasets | Develop retraining pipeline and apply training datasets |
| April 1 | Progress presentation, cross-reference predicted mutation with literature | Progress presentation, cross-reference predicted mutation with literature | evalute mean-squared error | evalute mean squared error |
| April 8 | Progress presentation | Progress presentation |  |  |
| April 15| Prepare final presentation and App Note | Prepare final presentation and App Note | Prepare final presentation and App Note | Prepare final presentation and App Note |
| April 22 | Practice final presentations, finalize App Notes |  |  |  |
| April 29 | |  |  |  |
