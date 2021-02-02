# Cybercrime
Notebook contains machine learning techniques to classify fraud clients.

**ATTENTION**: All data is private


## Data  
Two datasets were availiable:  
- hist_trx.csv - transaction history for 3 weeks
- hits0712.csv - fraud monitoring system activity

## Data preporation 
* Created one train data groupbying necessary columns
* Decoded mcc column using [mcc codes](https://mcc-codes.ru/)
* Used One-hot-encoding to features with small amount of unique values

## Feature engineering
* Splitted data to avoid data leaks
* Generated features based on date and amount of transaction

## Model
1. As a baseline used **XGBoost** with default parameters
2. Added custom function for parameters search with StratifiedKFold
3. Performed Hyper-Parameter tuning using **HyperOpt**
4. Found Top-10 features

## Sampling Experiments
Due to huge class disbalance I tried different Sampling Techniques from **imblearn**:
* ***SMOTE*** sampling
> This is oversampling tecnique using KNN. Data scalling is required. 
> Sampling strategy parameter is responsible for class ration in new data
* ***SMOTETomek*** sampling
> This sampling technique combines undersampling by **Tomek links** and oversampling by **SMOTE**

## TODO
* Train **XGBoost** on sampled data using **HyperOpt**
* Try **OPTUNA** for hyperparameter optimization, compare with **HyperOpt**
* Realize an adaptive surrogate modeling-based sampling. [ASMO](https://www.sciencedirect.com/science/article/pii/S1364815216310830)
