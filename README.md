# P-gp-Substrates-Prediction-Model
Machine learning-based prediction model for P-glycoprotein substrate prediction in early stage drug discovery

## Introduction ## 

Welcome to our repository, here we provide machine learning model to efficiently predict the P-glycoprotein (P-gp) substrate of target drug compounds in early stage of drug discovery process.
P-gp is an important membrane-bound transporter protein that plays a crucial role in the absorption, distribution, and excretion of many drugs. Predicting whether a compound is a P-gp substrate helps determine its absorption and distribution in the body.

## Classification criteria ##
<strong>The model uses an efflux ratio threshold:</strong>

The model classifies a compound based on its predicted efflux ratio value. If the efflux ratio is greater than or equal to 2, the compound is classified as class 1; otherwise, it is classified as class 0. 

Additionally, the model provides the probability that each compound belongs to its respective class. If classified as class 1, the compound is identified as a "substrate" of P-glycoprotein, along with the associated probability.
The efflux ratio (ER) is defined as the ratio of secretory permeability to absorptive permeability: 

𝐸𝑅= P<sub>app</sub>(a→b) / P<sub>app</sub> (b→a) 

where P<sub>app</sub>(a→b) represents permeability from the apical to the basolateral side (absorption) and P<sub>app</sub> (b→a) represents permeability from the basolateral to the apical side (secretion).

## Dependencies ##

- Python ≥ 3.9
- scikit-learn ≥ 1.26.4
- numpy == 11.5.0
- hpsklearn == 1.0.3
- hyperopt == 0.2.7
- xgboost == 2.0.3
- rdkit
- pandas

## Execution ##
**To run the prediction:**

```
$ python model.py --prediction --file_name [filename] 
```
<strong>Note:</strong> For the prediction step, prepare a .csv file containing SMILES without bioclass (e.g., test_set.csv)

**To run the validation:**

```
$ python model.py --validation --file_name [filename] 
```
<strong>Note:</strong> For the validation step, prepare a .csv file containing SMILES with bioclass (0 or 1) (e.g., valid_set.csv)

**Output:**

Our model generates output in binary value (1 or 0), where 1 indicates compound to be substrate, while 0 indicates non-substrate.

Additionally, the model provides the probability that each compound belongs to its respective class. If classified as class 1, the compound is identified as a "substrate" of P-glycoprotein, along with the associated probability.
 
**Please ensure that all the necessary files (P_gp_subs.pkl, data_preprocessing.py, scaler, features.txt, inputfile.csv) are kept in the working directory**
