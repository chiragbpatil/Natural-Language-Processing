# TF-IDF

TF-IDF is a technique used in Natural Language Processing (NLP) to determine the importance of a word in a document or corpus. It is based on the assumption that the importance of a word in a document is directly proportional to the number of times it appears in the document, and inversely proportional to the number of documents in the corpus that contain the word.

The calculation of TF-IDF involves two main components: Term Frequency (TF) and Inverse Document Frequency (IDF).

## Term Frequency (TF)
Term Frequency is a measure of how frequently a term appears in a document. It is calculated as the number of times a term appears in a document divided by the total number of terms in the document.

For example, suppose we have a document that contains 100 words, and the term "cat" appears 5 times in the document. Then, the TF for "cat" in that document would be:

TF("cat") = 5 / 100 = 0.05

The TF value for a term can range from 0 to 1. A higher value indicates that the term is more important in the document.

## Inverse Document Frequency (IDF)
Inverse Document Frequency is a measure of how rare a term is across all the documents in a corpus. It is calculated as the logarithm of the total number of documents in the corpus divided by the number of documents that contain the term.

IDF(t) = log(Total number of documents) / (Number of documents with term t in it)

for numerical stabiltiy we will be changing this formula little bit.

IDF(t) = log(Total number of documents / (Number of documents with term t in it + 1)) +1


For example, suppose we have a corpus of 1,000 documents, and the term "cat" appears in 100 of them. Then, the IDF for "cat" would be:

IDF("cat") = log(1000 / (100 + 1)) + 1= log(10) = 3.29263

The IDF value for a term can range from 0 to infinity. A higher value indicates that the term is more rare across the corpus.

## TF-IDF Calculation
The TF-IDF score for a term in a document is the product of its TF and IDF values. The formula for TF-IDF calculation is:

TF-IDF = TF x IDF

For example, if we have a document with a TF of 0.05 for the term "cat" and an IDF of 1 for the same term, then the TF-IDF score for "cat" in that document would be:

TF-IDF("cat") = 0.05 x 1 = 0.05

The TF-IDF score can be used to identify the most relevant terms in a document or corpus. The higher the TF-IDF score of a term, the more significant it is in the document or corpus.

## TF-IDF vectorization

TF-IDF vectorization is a process of converting a collection of text documents into numerical vectors, where each vector represents a document and the values in the vector represent the TF-IDF scores for the terms in that document.

TF-IDF vectorization involves the following steps:

1. Tokenization: The text is split into individual words or tokens.

2. Stop Word Removal: Commonly used words such as "the", "and", and "is" are removed from the text as they do not carry much meaning.

3. TF-IDF Calculation: The TF-IDF score is calculated for each term in each document.

4. Vectorization: The TF-IDF scores for each document are stored in a numerical vector representation.

For example, suppose we have a collection of three documents:

Doc 1: The cat in the hat
Doc 2: The cat ate the mouse
Doc 3: The mouse ran away from the cat

The TF-IDF vectorization process for this collection of documents would involve the following steps:

1. Tokenization:\
\
Doc 1: The cat in the hat
        ["The", "cat", "in", "the", "hat"]
Doc 2: The cat ate the mouse
        ["The", "cat", "ate", "the", "mouse"]
Doc 3: The mouse ran away from the cat
        ["The", "mouse", "ran", "away", "from", "the", "cat"]
        
2. Stop Word Removal:

        Doc 1: cat hat
        Doc 2: cat ate mouse
        Doc 3: mouse ran away cat
    
3. TF-IDF Calculation:
                ate         hat      ran      away       mous       cat   
        Doc 1:  0.         0.2810    0.       0.         0.         0.1424
        Doc 2:  0.2810     0.        0.       0.         0.2        0.1424
        Doc 3:  0.         0.        0.2007   0.2007     0.1428     0.1017

4.Vectorization:

        Doc 1: [0.    ,  0.2810,  0.    ,  0.    ,  0.    ,  0.14246359]
        Doc 2: [0.2810,  0.    ,  0.    ,  0.    ,  0.2   ,  0.14246359]
        Doc 3: [0.    ,  0.    ,  0.2007,  0.2007,  0.1428,  0.1017597 ]



## Applications of TF-IDF
TF-IDF is a widely used technique in NLP applications such as information retrieval, text mining, and document classification. It can help improve the accuracy and effectiveness of many NLP applications by identifying the most relevant terms in a large corpus of text.

Some common applications of TF-IDF include:

- Convert text into numerical vector 

- Document classification: TF-IDF can be used to identify the most important terms in a document, which can then be used to classify the document into a specific category or topic.

- Information retrieval: TF-IDF can be used to rank the relevance of documents to a user's query in a search engine.

- Text mining: TF-IDF can be used to identify the most important terms in a large corpus of text, which can then be used for clustering, topic modeling, and other text mining tasks.
