# document_classification
This is a collection of scripts for doing sentiment analysis (i.e. document classification). 

# using the scripts
All of these functions take CSV files as their input and convert them to Pandas DataFrames before model training; this is largely to facilitate data transfer between R and Python. As of now, the CSV files must be in a document-level format, i.e. with one row per document and a minimum of two columns, one holding the document text, and the other holding the outcome or target variable. The functions use sklearn's built in count vectorizers to vectorize the text data, which you can manipulate via the command-line arguments in the modeling scripts.    

# included scripts
  1. functions.py includes functions for training, testing, and tuning supervised document classification models
  2. nbsvm.py implements Wang and Manning's (2012) interpolated multinomial naive Bayes/support vector machine to.
  3. rf.py performs the same task as the NB-SVM, only using a random forest as the classifier instead of an SVM.
  
# example
This bash command will train an NB-SVM on the imaginary docs.csv using the values in the 'sentiment' column as the target and the text in the 'text' column as the input. 

$ python nbsvm.py '~/data/docs.csv' 'sentiment' 'text' -lm 'no' -ng 3 -sm 'train-test'

The optional arguments specify that vectorizer should not limit the number features it considers; that the maximum n-gram size should be 3; and that the data should be split using sklearn's train_test() function. See readme for nbsvm.py for more details.

# required modules
To run these scripts, you'll need the Pandas, ScikitLearn, and Scipy/Numpy modules in addition to a working installation of Python.
