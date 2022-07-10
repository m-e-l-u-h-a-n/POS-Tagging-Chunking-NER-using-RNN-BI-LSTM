**Name:** Purushottam Tiwari
**Roll No.:** 19074029
**Branch:** CSE(IDD)

### Description of the Lab Task:
The aim of this task was Part-of-Speech (POS) Tagging, Chunking and Named Entity Recognition (NER) using RNN and Bi-LSTM.

**NOTE:** Due to huge sizes of models and limited network constraints I had to cmplete the whole assignment through **google colab** so I have not downloaded the models. They are in my drive folder, link for which is: [https://drive.google.com/drive/folders/1oi2FPeGTrePAF-oUPSjDW8jagOeJdy7T?usp=sharing](https://drive.google.com/drive/folders/1oi2FPeGTrePAF-oUPSjDW8jagOeJdy7T?usp=sharing)
Submission folder only containes `.ipynb` files in corresponding folders.

## Part-of-Speech (POS) Tagging:
Part-of-Speech (PoS) tagging, then it may be defined as the process of assigning one of the parts of speech to the given word. It is generally called POS tagging. In simple words, we can say that POS tagging is a task of labelling each word in a sentence with its appropriate part of speech.

There are various methods for POS tagging, in this task we use two of them i.e. **SimpleRNN** and **Bi-LSTM**:
I have first dscribed the data processing part and then model.
#### Data processing:
* We first load the conll2000 dataset using nltk.
* Then we divide the data in words(X) and tags(Y).
* Then we vectorise both X and Y by tokenization.
* Then in order to have uniformity in the dimensions of input and output data we apply padding to both X and y.
* Then we load the pretrained word embeddings from [https://nlp.stanford.edu/projects/glove/.](https://nlp.stanford.edu/projects/glove/)
* Then we use gensim library to transform the loaded glove embedding, so that they can be used as normal(skipgram or cbow) like wordembedding.
* Then we map our input words with their corresponding word vectors.
* Then we split our data into ***train***, ***test***, and ***validation*** set.

### Model defnition:
* #### Model for SimpleRNN:
    It is a simple ***sequential*** model with an ***Embedding***, ***SimpleRNN***, and ***TimeDistributed*** layer.
* #### Model for RNN with Bi-LSTM:
    It is a simple ***sequential*** model with an ***Embedding***, ***Bidriectional LSTM***, and ***TimeDistributed*** layer.

### Results:
* SimpleRNN:
    - Training set
    **Loss**: 0.0141,
    **Accuracy**: 0.9963
    - Testing set
    **Loss**: 0.0220,
    **Accuracy**: 0.9934
* RNN with Bi-LSTM:
    - Training set
    **Loss**: 0.0189
    **Accuracy**: 0.9951
    - Testing set
    **Loss**: 0.02940
    **Accuracy**: 0.9913

## Chunking:
Chunking is a process of extracting phrases from unstructured text. Instead of just simple tokens which may not represent the actual meaning of the text, its advisable to use phrases such as “South Africa” as a single word instead of ‘South’ and ‘Africa’ separate words.

There are various methods for POS tagging, in this task we use two of them i.e. **SimpleRNN** and **Bi-LSTM**:

**NOTE:** Nearly all the steps for data processing, model definition and training were same as that for POS Tagging so they are repeated here again. Only result is mentioned.
### Results:
* SimpleRNN:
    - Training set
    **Loss**: 0.0424
    **Accuracy**: 0.9875
    - Testing set
    **Loss**: 0.0557
    **Accuracy**: 0.9820
* RNN with Bi-LSTM:
    - Training set
    **Loss**: 0.0321
    **Accuracy**: 0.9911
    - Testing set
    **Loss**: 0.0457,
    **Accuracy**: 0.9860

## Named Entity Recongnition:
Named Entity Recognition is a process where an algorithm takes a string of text (sentence or paragraph) as input and identifies relevant nouns (people, places, and organizations) that are mentioned in that string.

There are various methods for POS tagging, in this task we use two of them i.e. **SimpleRNN** and **Bi-LSTM**:

**NOTE:** Nearly all the steps for data processing, model definition and training were same as that for POS Tagging so they are repeated here again. Only result is mentioned.

The only difference was that data was loaded from a file `eng.train` and then processed in same way.
### Results:
* SimpleRNN:
    - Training set
    **Loss**: 0.0113
    **Accuracy**: 0.9968
    - Testing set
    **Loss**: 0.0168
    **Accuracy**: 0.9950
* RNN with Bi-LSTM:
    - Training set
    **Loss**: 0.0082
    **Accuracy**: 0.9978
    - Testing set
    **Loss**: 0.0457,
    **Accuracy**: 0.9860