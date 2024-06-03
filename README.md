# Sentiment Analysis performed on Drug Reviews

This is a project whose main goal is to estimate if a review of a given drug is positive or negative, as well as the occurence of positive or negative terms. This project uses this [Drug Review Database](https://www.kaggle.com/datasets/mohamedabdelwahabali/drugreview) for all required steps.

### 1. Overview

This project is composed of three parts: data analysis, data processing, and model training and evaluation. In the data analysis part, the imported data is explored and its general shape and behaviour are analysed. In the data processing part, the text is properly processed and converted to a structure which can be used to train a model. In the model training and evaluation part, a model was built, trained and later its performance is evaluated.

### 2. Project Step-by-step

First of all, the data to be used was imported to a local machine. After that, the data was loaded and was explored. It was checked if it contained any rows with empty values, and then it was verified its data distribution by rating and number of words per review. As the data was already divided into training, validation and test sets from the source, both exploratory analysis and data processing had to be separately performed for each set.

After finishing the data analysis, the three sets were processed. First, the relevant information was selected. Later, special characters and digits were removed, the text was converted to lower case, punctuation was removed, as well as stopwords, and finally a lemmatiser was applied to each word for each review. Then, the text was converted to a sequence of numbers using the train set as a base for the process.

Once converted the data into an adequate format, a model using Keras' LSTM object was built and trained. After trained, the model was saved and evaluated to check its performance for a few metrics. Finally, three lists for checking number of positive, neutral, or negative terms were created, and the model was tested on individual cases.

### 3. Challenges

During the project's work, two issues proved to be the most relevant for the project's progress. The first of them were the limited resources, which delayed the conclusion of the initial version. Before using the LSTM approach, simpler classifiers and even a BERT model were tried. The simpler classifiers didn't perform as well as expected, and the BERT model required a computing power which couldn't be obtained at the time, turning it unusable under present circumstances. Then, as a last resource, the LSTM approach was performed, and it proved to be decent in general.

The second issue, and also likely the hardest to deal with, was the data imbalance. Considering the basic binary classification approach, there were about 4 positive reviews for each negative one. When attempting the simpler classifiers, undersampling and oversampling techniques were used, but none of them showed any positive impact. When using the LSTM approach, class weights were used. This has led the model to perform better, but it still struggled to properly identify and classify the minority class.

### 4. Conclusion and Next Steps

The sentiment analysis model has a decent performance (overall accuracy of 75-76%), despite not being as reliable as desired when dealing with the minority class. In order to solve the issues regarding the data imbalance and improve even more the model's performance, a few iterations are suggested to adjust the class weights and other training parameters, like the number of epochs and the implementation of the early stopping. Also, other analysis steps can be added to complement the number of positive/neutral/negative terms in each review, which has room for improvement by itself.

