# Word Sentiment Analyzer

## Software used: Anaconda- Jupyter                                                                            
## Language Used: Python

In this Report, Two Machine Learning libraries were used to complete all the tasks as mentioned. Both the models were trained for the processing of data as per the need. 
These models were used to classify the data features (Questions) for the specific top-level label target (Suggestion, Requests, Attitudes and emotions, Hypothetical scenario, Rhetorical questions). The first model used for the process was RandomForestClassifier and the second one was Support Vector Classification – SVC. Both the models were tested on both the preprocessed and non-preprocessed data.
For splitting the data into test and training sets, 90-10 ratio is used, that is 90% is in the training set, and the rest 10% was in the test set of the model.
All the performance evaluation that has been calculated is done by using the 10-fold cross-validation method.

## Data cleaning process

All the data in the Column “Questions” was preprocessed, for preprocessing of data many steps were followed:
* Converting all the feature variable data into String: This was done to get all the data in the same format for better predictions in the model.
* Converting all the characters to lower: This was done so that all the data in the specific column is at the same level.
* Removing punctuation marks: The punctuation marks can make the same data interpret differently, so to neglect this the process was followed.
* Removing Stop Words: The commonly occurring words as ‘a’, ‘is’ etc. don’t provide much valuable information in the model so they were removed.
* Removing frequent words: Some words might be very frequent just like stop words, so removal of those was also mandatory.
* Removing rare words: All the words that rarely occur, do not create much of a difference so they were removed.
* Stemming and Lemmatization: All the derived words were removed with the help of this procedure.

## Evaluation Results

After using this model in the provided dataset after data preprocessing, following scores for performance evaluation arrived:

1. Evaluation / Models	Baseline (Random forest) - with Text Pre-processing	Baseline (Random forest) – without text preprocessing
  * Accuracy :	52 % , 	58.11 %
  * Precision :	45.86% ,	54.72 %
  * Recall :	52.02% ,	58 %
  * F1-score :	46.85% ,	55.67 %


2. Evaluation/Models	Improved (SVM) Model - with Text Pre-processing	Baseline (Random forest) – with text preprocessing
  * Accuracy :	53.16% ,	52.03 %
  * Precision :	45.43% ,	45.86 %
  * Recall :	53% ,	52 %
  * F1-score :	43.77%	, 46.8 %


3. Evaluation/Models	Improved (SVM) Model - without Text Pre-processing	Baseline (Random forest) – without text preprocessing
  * Accuracy :	63.29 % ,	58.11 %
  * Precision :	57.03 % ,	54.72 %
  * Recall :	63.51 % ,	58 %
  * F1-score :	59.42 % ,	55.67 %
