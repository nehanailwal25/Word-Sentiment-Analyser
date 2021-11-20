Software used: Anaconda- Jupyter                                                                            Language Used: Python

In this Report, Two Machine Learning libraries were used to complete all the tasks as mentioned. Both the models were trained for the processing of data as per the need. 
These models were used to classify the data features (Questions) for the specific top-level label target (Suggestion, Requests, Attitudes and emotions, Hypothetical scenario, Rhetorical questions). The first model used for the process was RandomForestClassifier and the second one was Support Vector Classification – SVC. Both the models were tested on both the preprocessed and non-preprocessed data.
For splitting the data into test and training sets, 90-10 ratio is used, that is 90% is in the training set, and the rest 10% was in the test set of the model.
All the performance evaluation that has been calculated is done by using the 10-fold cross-validation method.
All the data in the Column “Questions” was preprocessed, for preprocessing of data many steps were followed:
o	Converting all the feature variable data into String: This was done to get all the data in the same format for better predictions in the model.
o	Converting all the characters to lower: This was done so that all the data in the specific column is at the same level.
o	Removing punctuation marks: The punctuation marks can make the same data interpret differently, so to neglect this the process was followed.
o	Removing Stop Words: The commonly occurring words as ‘a’, ‘is’ etc. don’t provide much valuable information in the model so they were removed.
o	Removing frequent words: Some words might be very frequent just like stop words, so removal of those was also mandatory.
o	Removing rare words: All the words that rarely occur, do not create much of a difference so they were removed.
o	Stemming and Lemmatization: All the derived words were removed with the help of this procedure.

All the three different aspects go like this:
	Baseline with text preprocessing process – baseline
For this, the baseline (i.e manual implementation that was in the paper) was taken a step further by considering the RandomForestClassifier model for performing the classification.
This model was chosen because of its robustness, the RandomForestClassifier model makes use of multiple decision trees to make the best possible prediction of data, because of which versatility, the model can handle a large amount of data.




After using this model in the provided dataset after data preprocessing, following scores for performance evaluation arrived:

Evaluation / Models	Baseline (Random forest) - with Text Pre-processing	Baseline (Random forest) – without text preprocessing
Accuracy	52 %	58.11 %
Precision	45.86%	54.72 %
Recall	52.02 %	58 %
F1-score	46.85%	55.67 %

This model was also implemented without performing any text preprocessing on the data. Comparatively, the model without any text-preprocessing was working better than the text-preprocessed data.
More precisely, in between the model with preprocessed and non-preprocessed data, it’s visible that the accuracy dropped down from 58.11% to 52%, which is a huge fall.
Mostly, this is because the dataset that was used was not that huge and when the needed text-preprocessing was performed on the same, so it lost some important features that might have helped it in the classification.
Text processing has not proved to be such a great option in this specific implementation because of the lack of an efficient quantity of test and training datasets.

	Improved model with text preprocessing process – examine if your design improves the baseline
For this point, for doing improvement in the model a different upgraded model was used. Before going to the final selected model many models (namely, Logistic regression, KNeighbors, DecisionTree, Support Vector Classifier etc.) were taken into consideration but after rigorous analysis, the best model among all of these was found to be the Support Vector Classification (SVC) model and was considered for further implementation.
The implemented model has shown some minor improvement over the baseline model with text-preprocessing.

The performance evaluation scores for both models are as:

Evaluation/Models	Improved (SVM) Model - with Text Pre-processing	Baseline (Random forest) – with text preprocessing
Accuracy	53.16 %	52.03 %
Precision	45.43 %	45.86 %
Recall	53 %	52 %
F1-score	43.77 %	46.8 %


By the scores, it was easily visible that the performance of the model has improved somewhat well in terms of accuracy but still the precision for the model is the same.
I cannot say that this model is a huge success but considering the size of data is implemented, it seems to be a reliable model.
This model is working better because the data in the CSV is already a sparse (easily classifiable) set of data and once performed our preprocessing it became more sparse (i.e it became even easy to classify), though the quantity of data was reduced, but the connection of features to target variables was made better by preprocessing and SVM always works best when the data is sparse.
It can be said that this model worked better but not the best as again the only drawback that is there is that the dataset is small. This is one of the failure points I think that is happening with the model.
Some top-level matches were even having just a few Questions marked to them like ‘surprise’ was having just one question. 
So, this is the one thing that I guess has restricted the whole training process on the dataset immensely.


	Improved model without text preprocessing process – examine if text preprocessing helps or not
For this part, I have used again the same model as above i.e Support Vector Classifier but this time no preprocessing of data was done.
Here both the models, i.e Random forest and Support Vector were performed but again as the data was easily classifiable to some extent, so the SVM overpowered the base model well.

Evaluation goes like:
Evaluation/Models	Improved (SVM) Model - without Text Pre-processing	Baseline (Random forest) – without text preprocessing
Accuracy	63.29 %	58.11 %
Precision	57.03 %	54.72 %
Recall	63.51 %	58 %
F1-score	59.42 %	55.67 %

As it is visible from above, the SVM was proved to be better in mostly all the aspects over the Baseline even without any data preprocessing steps on the dataset.
The improved model(SVM) has proved to be having around 5% better accuracy rate than the baseline, which is great to achieve.
Support Vector model is having a great precision score than the Random Forest Classifier as well.
The implemented improved model would have performed even better on a large set of this data, as it is easily seen here that SVM is leading the Randomforest classier in numbers hugely.

I can say that the data that is provided in the dataset is easily classifiable to some extent that is the reason that SVM is always overpowering the baseline.
Though I think that this accuracy could have been even better if we had more data, then the model would be having more sets to get trained from.
I think that if more features were provided provide in the CSV, i.e if every top-level label would be marked to at least 200-300 questions, we would have made a better model by training on the huge amount of dataset. The cons of having just one or two features (i.e questions) getting marked to just one kind of top-level label (i.e. target) would have not been shown up and the model would be able to perform better. Basically, the cases like the ‘surprise’ top-level getting marked to just one Question would have been neglected.
