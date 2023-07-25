# Word2Vec CBOW

- Word2Vec is a widely-used model for learning word embeddings, which are dense vector representations of words that capture their semantic and syntactic properties. The continuous bag-of-words (CBOW) model is a specific type of Word2Vec model that predicts a target word given its context words.

- The CBOW model takes as input a sequence of words and generates a set of training examples, where each training example consists of a target word and its context words. The context words are selected based on a window size parameter, which determines how many words to the left and right of the target word to consider.

- For example, given the sentence "the quick brown fox jumps over the lazy dog" and a window size of 2, the training examples generated for the word "fox" would be:

        (["quick", "brown", "jumps", "over"], "fox")
        (["the", "brown", "fox", "over"], "jumps")
        (["quick", "fox", "jumps", "the"], "brown")
        (["brown", "fox", "over", "lazy"], "jumps")
        
- The CBOW model then learns to predict the target word given its context words, by minimizing a loss function such as negative log-likelihood. The model achieves this by training a neural network with an input layer that takes the context words as input, a hidden layer that generates the embeddings, and an output layer that predicts the target word.

- The embeddings learned by the CBOW model can be used for a variety of downstream tasks, such as text classification and information retrieval. One advantage of the CBOW model over the skipgram model is that it is faster to train and uses less memory, making it more suitable for large datasets. However, the skipgram model is generally considered to be more accurate for rare words and phrases.