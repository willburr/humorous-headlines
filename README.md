# Humorous Headlines

Our approach to Task 2 (determining the funnier of two edited headlines) in https://competitions.codalab.org/competitions/20970.

We tackled Task 2.

*Important note:*

Any of our models for section 1 can be run independently of each other, however all of the cells in the Project Setup and Data Augmentation & Vocab Preparation sections needs to be run as a prerequisite. 

For section 2, the model for 1.1 is reused, and so this definition needs to be rerun also.

Each model roughly consists of:
- Creating some kind of data loader & initialising embeddings
- Defining the model
- Setting hyper parameters
- Training the model
- Getting predictions on the test set

Here is an overview of the structure of this notebook, and how to run each section.

More details on the models in the report, and more fine-grained details above each individual cell. 

## Project Setup

This section needs to be run to train any models, and downloads/imports/sets up everything needed.

## Data Augmentation and Vocab Preparation

This section also needs to be run to train any models - it prepares all of the data and runs a lot of housekeeping methods

## 1: Approach 1 - Pre-Trained Representations

### 1.1: Model 1.1: Bi-directional LSTM with GloVe Embeddings

This model needs the `Project Setup` and `Data Augmentation and Vocab Preparation` sections to be run first.

#### Data Manipulation Evaluation

This experiment is mentioned in the report. It needs model 1 to have been trained. It takes around an hour, as it trains model 1 multiple times in multiple configurations.
We evaluate the performance of:

- Punctuation removal
- Stopword Removal
- Training sentence pair flipping

We do this only on our first model to keep consistency, and this can be run once Model 1.1 and everything before it has been run.

It produces and downloads box plots. 

### 1.2: Model 1.2: Bi-directional LSTM with DistilBERT Embeddings

This model needs the `Project Setup` and `Data Augmentation and Vocab Preparation` sections to be run first.

### 1.3: Model 1.3: Fine-tuning DistilBERT

This model needs the `Project Setup` and `Data Augmentation and Vocab Preparation` sections to be run first.

## 2: Approach 2: No Pre-Trained Representations

## 2.1 Baselines

We have some initial baselines given in the skeleton code, and then we implemented two neural models:

## 2.2 Neural Models

These models use the bi-directional LSTM from part 1.1, so the cell with the definition of this model needs to be run.

This model also needs the `Project Setup` and `Data Augmentation and Vocab Preparation` sections to be run first.

## Evaluation

This final section has the evaluation tests between our best performing models for tasks 1 (BiLSTM + BERT) and 2 (LSTM with attention), looking at:

- Loss Curves
- Accuracies
- Confusion Matrices
- F1 Score

To run these, you need to train models 1.2 and 2.2 as explained how to in their sections
