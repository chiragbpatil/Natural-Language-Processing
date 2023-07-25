# Bag of Words in NLP

In Natural Language Processing (NLP), Bag of Words (BoW) is a popular technique for text representation. The BoW model is based on the idea that a text can be represented as a bag of its words, disregarding grammar, word order, and context, but keeping track of their frequency. This approach is often used for text classification, sentiment analysis, and information retrieval.

How does it work?
The BoW model consists of the following steps:

1. Tokenization:\
The first step in the BoW model is tokenization. Tokenization is the process of breaking up a text into individual words or tokens. The tokenizer can be word level by splitting the text on whitespace or at character level, or it can be more complex, using techniques like stemming, lemmatization, and part-of-speech tagging. splitting at whitespace may not work languages like chienes, thai etc as they are not consistently use space as delemeter.

2. Vocabulary creation:\
The second step in the BoW model is vocabulary creation. A vocabulary is created from all the unique words or tokens in the text corpus. This vocabulary is used to represent each document as a vector of the same length as the vocabulary.

3. Vectorization:\
The third step in the BoW model is vectorization. Each document is represented as a vector of the same length as the vocabulary, where each element corresponds to the frequency of a particular word in the document. This means that the vector for each document is sparse, with most elements being zero.

For example, suppose we have the following two documents:\

Doc 1: The cat in the hat\
Doc 2: The dog on the log

The BoW model would represent these documents as follows:

Vocabulary: {the, cat, in, hat, dog, on, log}

Doc 1: [1, 1, 1, 1, 0, 0, 0]\
Doc 2: [1, 0, 0, 0, 1, 1, 1]

In this example, the vocabulary consists of seven unique words, and each document is represented as a vector of length seven. The vector for Doc 1 has a value of 1 for each of the words "the", "cat", "in", and "hat", and a value of 0 for the remaining words. The vector for Doc 2 has a value of 1 for each of the words "the", "dog", "on", and "log", and a value of 0 for the remaining words.

# Limitations
The BoW model has several limitations, including:

- Ignoring word order and context can lead to a loss of meaning.
- Stop words (common words like "the" and "and") can dominate the vector and distort the meaning.
- Rare words may not be included in the vocabulary or may have very low frequencies, leading to poor representation.

