# Sentiment Analysis with PyTorch
The repository will walk you through the process of building a Sentiment Analysis model, which will be able to predict a polarity of given review (whether the expressed opinion is positive or negative). The dataset on which the model is going to be trained is popular IMDb movie reviews dataset.
Table of contents
•	Data pre-processing
  The first notebook covers data loading from the raw dataset (separated to multiple files of positive and negative labeled reviews). Text preprocessing and split to   train/val/test sets preparation.
•	Pre-processing steps included
o	Cleaning of special characters and digits
o	Stemming
o	Stop words removal
o	Split to the test/train and validation sets
o	Creating dataset's vocabulary
o	Length standardization – we limited review length to decrease model training time
o	Too short reviews were padded with zeroes to be in the same length as all the other reviews
o	All the words were mapped words to their numerical representation (word2index) and reverse (index2word)
o	Enablinged the use of pre-trained word vectors (from genism library)
o	Reviews prep for model training were done with Pytorch DataLoader.
o	Pytorch Embeddings were initialized with genism weights 
•	LSTM model
We have created a LSTM class that inherits from nn.Module and instance its parameters and weight initialization. Our module is composed of a cell, an input gate, an output gate and a forget gate. The cell remembers values over arbitrary time intervals and the three gates regulate the flow of information into and out of the cell.
Dataset
Dataset is available under the following link: http://ai.stanford.edu/~amaas/data/sentiment/
We rearranged the data to the following structure:
![image](https://user-images.githubusercontent.com/93888640/164790181-9e43ed18-39f9-403f-86b6-4e17a777cd09.png)
  
Models:
The embedding vectors we imported via gensim:

•	Word2vec-google-news-300 Vectors:

  This word2vec model was trained by Google on the Google News dataset, on about 100 billion words. The model contains 3,000,000 unique phrases built with layer size of 300.
  
•	Glove-Twitter -100 Vectors: 

  These GloVe embeddings trained on a Twitter dataset. These vectors are based on 2B tweets, 27B tokens, 1.2M vocab, uncased. The original source of the embeddings can be found here:
  
  https://nlp.stanford.edu/projects/glove/

Results will be discussed in main.ipynb.
