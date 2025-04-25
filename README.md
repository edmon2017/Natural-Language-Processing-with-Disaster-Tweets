# Natural-Language-Processing-with-Disaster-Tweets

In this exercise I'm going to build a model that predicts which Tweets are about real disasters and which ones are not, using the data from Kaggle competition:

https://www.kaggle.com/competitions/nlp-getting-started/overview

The available data is organized in two files; train and test, with the text of the Tweets and the classification: 1 when it is about a real disaster and 0 when is not.

## EDA

After the EDA, I found this main observations:

* There are 7613 recoard, the column called 'text' cotains the tweets and 'target' the classification

* Very few missing tweets.

* Class imbalance: typically ~60/40 split.

* Most tweets are under 30 words.

* Data was cleaned.

![image](https://github.com/user-attachments/assets/e458fae9-d974-4422-a6c0-34e230793ecd)


## Model Architecture
For this exercise I'm going to use a recurent neural network (RNN). This because Tweets are short sequences of tokens with word-order patterns, and the RNN can learn these sequential dependencies. 

I'm going to use:

* Embedding layer (maps each token to a dense vector space; learned during training).

* Bidirectional LSTM and GRU (captures context from both left→right and right→left).

* Dropout (prevents over-fitting).

* Dense→Sigmoid (binary classification).

![image](https://github.com/user-attachments/assets/5e8b83ff-c500-41f0-beda-f2451986b695)

![image](https://github.com/user-attachments/assets/8ac3d0cf-0245-4477-a1ed-d968679e5813)

## Conclusions

In this exercise I create a model to classify dissarter tweets. In the process, the EDA and Cleaning revealed moderate class imbalance and short tweet lengths.

For the model I create a bidirectional RNN, in this case LSTM and GRU, had similar results. 

Some key point are:

* The highest validation AUC was close to 0.86.

* The best hyperparameters are 64 units and 100 dim embeddings.

* Early stopping and dropout were useful to prevent over-fitting.

Results could be improved using a pretrained embeddings.
