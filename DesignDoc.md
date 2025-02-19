# Mutation Prediction for Viral Proteomes (Design Document) 
Group project for COMP 383/483 - mutation prediction for viral proteomes with Dr. Whelton Miller. 

## Overview
- [ ] Viruses mutate extremely frequently, their mutation rate being higher than any other organism. Their ability to quickly evolve has lead to efficient infection of their host, evading antiviral drugs.
- [ ] Due to this characteristic, it has proven difficult to hault the spread of a virus, as seen with the spread of Sars-CoV-2. There is an urgent demand for the accurate predictive tools for viral mutations in order to get ahead of the virus and stop the spread prior to mutation.
- [ ] A previous group has worked with Dr. Miller to create a machine learning model for mutation prediction based on hidden mutation patterns. However, the current model is only fit for the Sars-CoV-2 virus. We aim to expand this model to fit other viruses; Human Papillomavirus (HPV) and Epstein-Barr virus (EBV).

### Current Machine Learning (ML) Model
- [ ] The current machine learning model was trained using the Sars-CoV-2 receptor binding domain.
- [ ] The tool extracts viral genomic sequences from NCBI and preprocesses the sequences to remove non-standard amino acids.
- [ ] The model uses a neural network with long short-term memory, convolutional neural network, and variational autoencoder to return mutational predicions with minimized loss function.
- [ ] To train the model, dimensionality was reduced, 4137 samples of Sars-CoV-2 variants were used in the training dataset, and hyperparameters were optimized.
- [ ] The performance of the model was evaluated in encoder dataframes. The mean-squared error and referencing predicted mutations with current literature were also used to evalute the model.

#### Challenge with the Current ML Model
- [ ] The current model has been trained with Sars-Cov-2 datasets and as such performs uniquely well with Sars-Cov-2 viral evolution. We however want to expand its capability to be applicable to other viral proteomes.
- [ ] To expand the toolkit to be applicable to different viruses, we will begin by testing the current tool and evaluating the accuracy of mutation prediction for HPV and EBV. To retrain the model for these viruses, we will use incremental learning techniques with small batches of data, including a new training dataset with HPV and EBV variants.
- [ ] We will achieve this with _**scikit-learn**_(https://scikit-learn.org/stable/), a python based machine learning model, via the _"partial_fit"_ method.
- [ ] We will evaluate the accuracy of the updated model, ensuring the mutation prediction is accurate for Sars-CoV-2, HPV, and EBV. Lastly, we will compile a summary of our project into a graphical output similar to a poster.
- [ ] If time allows, we will also revise the tool to make it more user-friendly by reducing the lines of code necessary to use the tool. The development of this tool will allow for a proactive approach when designing therapeutic approaches for viruses.

## Context
The susceptibility of microbes, including viruses, to continuous evolution poses a unique challenge to efforts aimed at therapeutic interventions to combat their illicited infections. Advances in Artificial Intelligence(AI) and Machine Learning(ML) has seen unique applications to dealing with currently pressing challenges, and in the context of health, its application in drug research and development offers interesting insights into how current and emerging infection(s) might be treated. 
Although there are tools to predict viral mutations, a unique setback for most of them is that they are unable to predict mutation effectively across different viral strains. Here, we aim to further refine the efficiency of an already-existing tool such that it is able to predict mutation across different viral strains/species. 

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
![11A](https://github.com/abright087/Mutation-Prediction/assets/57806377/ed296aad-de28-41dd-9414-d3ab4acad895)


The main steps in our project involve the following:
- [ ] _**Step 1 (Test and Evaluate the Model)**_
- First, test and evaluate the performance of the existing model on Sars-Cov-2.
- Output performance from this dataset will be used as our benchmark for later comparison with other viral proteomes. The performance metrics which we will use is the  mean sqared error value predictions.
- We will then retest the tool for other viral proteomes. Here, we will test its performance on Human Papilloma Virus(HPV) and EBV datasets.
- Comparing the performance metrics of both cases, we will assess how well it performed on the other datassets.
- Since Sars-Cov-2 was the initial training dataset, we expect prediction outcome of other viral proteomes to be less efficient than that of Sars-Cov-2.
- [ ] _**Step 2 (Refine the Model)**_
- Comparing results in each occasion to that of the original training dataset, we will try to optimize the performance of the model by either expanding the datapoints/unique variables from which inference of mutation could be made.
- We hope to achieve this by implementing the 'partial-fit' pipeline from 'scikit-learn'.
- We will continuously retest performance after its implementation to see for any improvements in prediction.
- [ ] _**Step 3(Generalize the Model)**_
- We finally will attempt to generalize the prediction model by testing it on different viral strains.
- We overall aim to generalize the tool such that it has optimum or near-optimum prediction capability across different viral proteomes.
      
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



## References

1. Scikit Learn (https://scikit-learn.org/stable/)
