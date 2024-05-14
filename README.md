# NLP-FlipitNews-article-category-classification

### Problem Statement:

**Context**:
The Gurugram-based FlipItNews aims to revolutionize the way Indians perceive finance, business, and capital market investment, by giving it a boost through artificial intelligence (AI) and machine learning (ML). They’re on a mission to reinvent financial literacy for Indians, where financial awareness is driven by smart information discovery and engagement with peers. Through its smart content discovery and contextual engagement, the company is simplifying business, finance, and investment for millennials and first-time investors

**Objective**:
The goal of this project is to use a bunch of news articles extracted from the companies’ internal database and categorize them into several categories like politics, technology, sports, business and entertainment based on their content. Use natural language processing and create & compare at least three different models.

### Attribute Information:

* Article
* Category

The feature names are themselves pretty self-explanatory.



## Solution:

1 . First import necessary libraries.
2. Perform EDA to see the most number of articles belonging to Business and sports categories.
3. ## Text Preprocessing
   Removing nonletters from every article
   Tokenizing every article to text
   Removing stopwords 
   And finally lemmatization
   Encoding every category from 1-5

4.## BOW
   Each row is converted to a document and each column is to all words(consider max_features = 5000 only 5000 most frequent words will be considered), cell counting frequency of word to each document.

5. Split train and test data(20 % data of train data belongs to test data)
6. ## ML models
   Naive Bayes Classifier:
    Train Accuracy: 0.98
    Test Accuracy: 0.97
   Decision Tree
    Train Accuracy: 1
    Test Accuracy: 0.862
   Nearest Neighbour Classifier:
    Train Accuracy: 0.96
    Test Accuracy: 0.93
   Random Forest Classifier:
    Train Accuracy: 1
    Test Accuracy: 0.955

Observation: Out of all the models tested till now, the Naive Bayes Classifier seems to be the best performing one since it gives good train & test accuracy, more than satisfactory precision & recall, and almost non-significant overfitting.

7. ## LSTM
#Parameters
max_features = 5000  #  max_features=5000 specifies that only the top 5000 most frequent words will be considered as features.
maxlen = 100  # Cuts off the text after this number of words # This variable specifies the maximum length of the sequences (or sentences) after tokenization. Any sequence longer than maxlen will be truncated to maxlen, and sequences shorter than maxlen will be padded with zeros.
embedding_size = 100  # Dimensionality of the GloVe embeddings
batch_size = 1000
epochs = 100

Every text is converted to lower case.
Word tokenization is being done according to LSTM.
pad_sequence to every article to 100 word length if length is greater than 100 cutoff. And if less than 100 padded to 0.
Load Glove embeddings of 6B word and 100 dimension
create an embedding matrix of 5000 words and 100 dimensions.
Build a LSTM model with 100 units, 20% dropout and 20% recurrent dropout.
Run for 38 epoch and got an accuracy 88%.
   
   
   
