## Assignment Summary
The Assigments include **Email Spam Classifier**, **Airline Tweet Sentiment Classifier** and **Implementation of CountVectorizer and TfidfVectorizer**.

## Comparison between my Implementation and Sklearn 
Now I will be comparing the scores of my implementations of CountVectorizer and TF-IDF with those available in Scikit-Learn library.
The results of CountVectorizer are same in both the difference is just in the indices of the words.

The results of TF-IDF vary significantly from that of the Scikit-Learn library as in Sklearn the formula used for IDF is smoothened and is as follows:

**IDF(t,D) = log((N + 1)/(df(t) + 1)) + 1**


In this formula the IDF it is never zero. Then it also uses L2 normalization where it divides the TF-IDF of each term the document with the norm of the TF-IDF values of all the terms in the document.

**TF-IDF(normalized) = TF-IDF(raw) / sqrt(\Sum(TF-IDF(raw)^2))**

The words like 'the' have 0 IDF as per my calculation as they appear in each document but in sklearn the IDF of 'the' will be 1 and TF is same as calculated by my implementation. After L2 normalization it will be a number in (0,1) but in my function the TF-IDF of 'the' will be zero. 
