# Tweet-sentiment-analysis

## Overview
Test of differents models to classify sentiment in tweet including Microsoft API, RNN, LSTM and a pre-trained model.

## Data
Dataset available [here](https://www.kaggle.com/datasets/kazanova/sentiment140).  
1 600 000 tweets.

## Data preparation 
The following filter were applied in both scripts :
* Stopwords with NLTK  
* ASCII characters removed  
* URI/mail  
* Repeating characters  
* Contraction (yallre ==> you are all) from this [package](https://pypi.org/project/pycontractions/)  
* Stemming  
* Occurence > 2  

Then for one model we tried without any punctuation
See this [notebook](https://github.com/Falco-ops/Tweet-sentiment-analysis/blob/master/master-ppss1.ipynb) 

And in the other one we use the emoji library to tokenize emoji with [NLTK tweet tokenizer](https://tedboy.github.io/nlps/generated/generated/nltk.tokenize.TweetTokenizer.html).
See this [notebook](https://github.com/Falco-ops/Tweet-sentiment-analysis/blob/master/master-pprss2.ipynb).  

# Model
We studied the impact of emoji on accuracy.
Regarding the model the following were tested :
* simple RNN layer
* LSTM Layer
One embedding layer pre-trained with the GloVe model were added with the model best performing model. We chose the model specially trained for tweets.

Logistic regression was also tested as a baseline. 

## Performance
Simple RNN : accuracy = 0.71
Logistic regression : accuracy = 0.778
LSTM : accuracy = 0.79
GloVe : Accuracy = 0.928

See [technical note](https://github.com/Falco-ops/Tweet-sentiment-analysis/blob/master/Technical_note.pdf) for more details
