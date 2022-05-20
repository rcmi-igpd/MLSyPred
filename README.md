# MLSyPred (Machine Learining Synergy Predictor tool) ©

We describe a MLSyPred framework, based on a data science lifecycle project, for creating models to predict drug synergy interactions for application in combinatorial therapies for any disease. 
It allows to include as many modules as needed to manage different data and computation methods for creating the predictive models. 
Several modules are currently implemented in each of the different lifecycle project phases to test the framework. 
These modules include generating the Morgan Fingerprints, creating the features, cleaning the raw data, solving imbalance data issues, selecting the most important feature, training and evaluating the ML algorithms, and obtaining the final models. 
This tool allows easy reproducibility of the process to obtain the models. 
It is flexible for incorporating different data types and other implementations of ML- models or mechanistic methods for synergistic drug combinations.

Contains:

# MLSyPred-COMBINATION PIPELINE
  The purpose of this script is to be able to perform average based on the presence of Morgan Fingerprints per pair of compounds.
  There are 2048 bit Morgan fingerprints (features) and 79 drug compounds.
 
 INPUT files:
  1. smiles_trainingset.csv
  2. smiles_validationset.csv
  3. COMBINATIONS_SYNERGY_TRAINING_3D7.csv
  4. COMBINATIONS_SYNERGY_TRAINING_DD2.csv
  5. COMBINATIONS_SYNERGY_TRAINING_HB3.csv
  6. COMBINATIONS_SYNERGY_VALIDATION_3D7.csv
  7. COMBINATIONS_SYNERGY_VALIDATION_DD2.csv
  8. COMBINATIONS_SYNERGY_VALIDATION_HB3.csv
 
 OUTPUT files:
  Available in the Supplementary Material

# MLSyPred ML Models Antimalarials PIPELINE V 0.9.6
  The purpose of the script is to identify the core implementation for learning the ML algorithms, evaluate and obtain the models and includes the ML algorithms: 
  Random Forest, Logistic Regression, Support-Vector Machine, AdaBoost and Gradient Boost
  The outcome of this script is to obtain the best performing ML algorithm per Plasmodium falciparum strain. 
  The best performing model per strain can be used to predict other synergistic drug combinations for the domain in which it was trained, for example, antimalarials or   any other drug combinatorial therapy.
  
 INPUT files:
  1. ALL_SET_ML_Morgan2048_3D7_UPDATED.csv
  2. ALL_SET_ML_Morgan2048_DD2_UPDATED.csv
  3. ALL_SET_ML_Morgan2048_HB3_UPDATED.csv
 
 OUTPUT files:
  The ML algorithms per Plasmodium falciparum strain (must be five csv files per strains pertaining to the 5 ML models described)
  Amoung the 5 csv files, the best performing ML algortihm must be chosen for the ML_Pipeline_Prediction_Runner

# ML_Pipeline_Prediction_Runner
  Must run after the MLSyPred ML Models Antimalarial PIPELINE V 0.9.6
  The output file of the best performing model per Plasmodium falciparum strain will be selected as the input for this Machine Learning Prediction Runner PIPELINE
 
 INPUT files:
  The best performing ML algorithm file obtained as the output of the MLSyPred ML Models Antimalarials PIPELINE V 0.9.6 (per Plasmodium falciparum strain)
  
 OUTPUT files:
    Predictions of new drugs

# Datasets used were provided from:

Mason, D. J., Eastman, R. T., Lewis, R., Stott, I. P., Guha, R., & Bender, A. (2018). Using Machine Learning to Predict Synergistic Antimalarial Compound Combinations With Novel Structures. Frontiers in pharmacology, 9, 1096. https://doi.org/10.3389/fphar.2018.01096

Mott, B. T., Eastman, R. T., Guha, R., Sherlach, K. S., Siriwardana, A., Shinn, P., McKnight, C., Michael, S., Lacerda-Queiroz, N., Patel, P. R., Khine, P., Sun, H., Kasbekar, M., Aghdam, N., Fontaine, S. D., Liu, D., Mierzwa, T., Mathews-Griner, L. A., Ferrer, M., Renslo, A. R., … Thomas, C. J. (2015). High-throughput matrix screening identifies synergistic and antagonistic antimalarial drug combinations. Scientific reports, 5, 13891. https://doi.org/10.1038/srep13891

# Authors

Abiel Roche-Lima, Angélica M. Rosado-Quiñones, María Del Mar Figueroa-Gispert, Jennifer Díaz-Rivera, Roberto G. Díaz-González, Kelvin Carrasquillo-Carrion, Roberto A. Feliu-Maldonado, Pedro Fernández-Gochez, Brenda G. Nieves-Rodríguez, Emilee E. Colón-Lorenzo, and Adelfa E. Serrano
