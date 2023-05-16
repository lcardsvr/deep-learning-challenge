# Deep Learning Challenge
Module 21 Challenge

### Step 1: Preprocess the Data

Data was preprocessed as requested.

### Step 1: Preprocess the Data

The information available in the database consisted of:

- 'EIN' and 'NAME'—Identification columns
- 'APPLICATION_TYPE'—Alphabet Soup application type
- 'AFFILIATION' —Affiliated sector of industry
- 'CLASSIFICATION'—Government organisation classification
- 'USE_CASE' —Use case for funding
- 'ORGANIZATION' —Organisation type
- 'STATUS' —Active status
- 'INCOME_AMT' —Income classification
- 'SPECIAL_CONSIDERATIONS' —Special considerations for application
- 'ASK_AMT' —Funding amount requested
- 'IS_SUCCESSFUL'—Was the money used effectively

 
 The non-beneficial ID columns, 'EIN' and 'NAME' were dropped. Cutoff values determined for the Application and Classification types. All the categorical data was converted to numerical using 'get_dummies'. 'IS_SUCCESSFUL' was used as the Target array and the rest of the columns as the features.

The dataset was then split into test and training sets and finally scaled using a Standard Scaler.


### Step 2: Compile, Train, and Evaluate the Model

A model as below was trained. the First layer with a ReLu activation function and the Second Hidden and Ouput layers with Sigmoid activation functions



|--- Layer (type)--|---                Output Shape---|--              Param #--|
|------------- | -----------------------------|-----------------------|
|dense_9 (Dense)|             (None, 10)       |         440       |
|dense_10 (Dense)|            (None, 10)       |        110       |
| dense_11 (Dense)|            (None, 1)       |         11       |
                                                                 
Total params: 561
Trainable params: 561
Non-trainable params: 0

With 30 Epochs modeled performed as below:

Loss: 0.5539029836654663, Accuracy: 0.7293294668197632

The obtained model can be found under https://drive.google.com/file/d/1ec-wpJwY6tPXds1lUCKLn1FDCpfHTBY8/view?usp=share_link . This is to fullfill the  AlphabetSoupCharity.h5 result requirement.


### Step 3: Optimise the Model

To try to optimise the model different sequential models were trained adding neurons and layer. A sweep from 1 to 30 neurons was used for the layers. The number of hidden layers changed from 1 to 6. Different epoch numbers were attempted but for the code presented, 30 were used with no significant change in the results.

The best model obtained had the parameters below:

{'activation': 'relu', 'first_units': 26, 'num_layers': 4, 'units_0': 6, 'units_1': 6, 'units_2': 16, 'units_3': 16, 'units_4': 21, 'tuner/epochs': 20, 'tuner/initial_epoch': 7, 'tuner/bracket': 1, 'tuner/round': 1, 'tuner/trial_id': '0018'}

The evaluated model provided the results below:

Loss: 0.5463535785675049, Accuracy: 0.7356268167495728.

Different attemps were performed with the steps outlined above in Steps 2 and 3. 


Different attempts were performed in different

A value of 0 in the “loan_status” column means that the loan is healthy. A value of 1 means that the loan has a high risk of defaulting. This is the variable that was used to predict. All the rest of the variables were used as input.

Data includes 75036 samples of healthy status and 2500 of high-risk. For the 2 layer model a Loss of 0.5578005909919739 and an Accuracy of 0.722449004650116 were obtained. 

The multi layer model of the parameters below was attempted with optimization

{'activation': 'sigmoid', 'first_units': 24, 'num_layers': 5, 'units_0': 25, 'units_1': 3, 'units_2': 8, 'units_3': 18, 'units_4': 29, 'units_5': 12, 'units_6': 9, 'units_7': 6, 'units_8': 6, 'units_9': 6, 'tuner/epochs': 30, 'tuner/initial_epoch': 0, 'tuner/bracket': 0, 'tuner/round': 0}

A Loss of 0.5759138464927673 and an Accuracy of 0.727580189704895 were obtained.

A copy of the best model information obtained can be found under https://drive.google.com/file/d/1--Zwey1-7setpBSXXB5XWRMyf_VGs19F/view?usp=share_link to comply with the AlphabetSoupCharity_Optimisation.h5 requirement


## Summary

The intention of the analysis was to create a binary classifier that could predict whether applicants would be successful if funded by Alphabet Soup.

### Data Preprocessing

1. What variable(s) are the target(s) for your model? As outlined above 'IS_SUCCESSFUL' was used as the Target array

2. What variable(s) are the features for your model? As above, the rest of the numerical columns were used as the features.

3. What variable(s) should be removed from the input data because they are neither targets nor features? The non-beneficial ID columns, 'EIN' and 'NAME' were dropped

### Compiling, Training, and Evaluating the Model

4. How many neurons, layers, and activation functions did you select for your neural network model, and why? An initial model with a first layer with a Relu function with the number of inputs of the train scaled target array and 10 neurons, along with a Second hidden layers of 10 neurons and a sigmoid activation function and an outut layer with one unit with sigmoid activation function was used. This was used as a wild guess.

5. Were you able to achieve the target model performance? A Loss of 0.5539029836654663 and an Accuracy of 0.7293294668197632 were obtained. The target accuracy of 75% was not achieved. 

6. What steps did you take in your attempts to increase model performance? To attempt to improve the performance models with a varying number of neural networks and hidden layers were attempted. The best result obtained had a Loss of 0.5463535785675049 and an Accuracy of 0.7356268167495728.


Varying the number of neurons and hidden layers did not improve the results drastically. It is possible that the variables available do not have much prediciting power for the task at hand or potentially have redundant information. A possible way forward could include performing Principal Component Analysis to try and extract more relevant information. Removing redundant information may simplify the model and provide better results.


## Submission

1. Jupyter notebooks with analysis submitted and available in GitHub under https://github.com/lcardsvr/deep-learning-challenge/blob/main/Starter_Code.ipynb and https://github.com/lcardsvr/deep-learning-challenge/blob/main/AlphabetSoupCharity_Optimisation.ipynb

2. Model results that needed to be saved available under https://drive.google.com/file/d/1ec-wpJwY6tPXds1lUCKLn1FDCpfHTBY8/view?usp=share_link . (To fullfill AlphabetSoupCharity.h5) and  https://drive.google.com/file/d/1--Zwey1-7setpBSXXB5XWRMyf_VGs19F/view?usp=share_link (to fullfill AlphabetSoupCharity_Optimisation.h5)