# n_gram_Language_Model

This code is an implementation of an N-gram language model, which can be used to predict the next word in a sequence based on the previous N-1 words. The language model is trained on a given dataset, and can be used to evaluate the perplexity of the model on a test set.

## Requirements
* Collections
* Math
* Random

## How to use
To use the language model, first load the data from a file:

`corpus = load_data("filename.txt")`

Then, tokenize the data by splitting the words on spaces:

`tokenized_corpus = tokenize(corpus)`

Next, create a Unigram model and train it on the tokenized corpus:

`unigram = Unigram()`

`unigram.train_unigram(tokenized_corpus)`

You can also specify a smoothing method (either "add-k" or "interpolation") and a value for the hyperparameter l1 when training the model:

Copy code
unigram.train_unigram(tokenized_corpus, smoothing="add-k", l1=0.1)
To evaluate the perplexity of the model on a test set, you can use the perplexity function:

`perplexity = unigram.perplexity(test_set)`

The language model also includes implementations for Bigram and Trigram models, which can be trained and evaluated in a similar way.

## Smoothing

The language model includes two methods for smoothing the probabilities of unseen words: add-k smoothing and interpolation. Add-k smoothing adds a constant value k to the count of each word, while interpolation uses a linear combination of the unigram, bigram, and trigram probabilities to estimate the probability of a word. The value of k or the weights for the interpolation can be specified using the hyperparameter l1.

## Evaluation
The performance of the language model is evaluated using perplexity, which is the exponentiated average log-likelihood of the model. A lower perplexity indicates a better fit of the model to the data.
