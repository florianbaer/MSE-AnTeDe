# Question Answers Lab 2

## Lab a

How does *keep_inflected* affect the output of __normalize__?
> *keep_inflected* does not lemmatize the text

3) What is the posterior probability of finding 'limmat' given that the document is tagged as 'zurich'? Complete the following code snippet to find out. Use *verbose* to see what's going on under the hood.
> The posterior probability is 0.17

Print out the prior probabilities and the posterior probabilities and answer the following questions:
a) What is the lowest posterior probability that you observe and why?
> (rhône, bern)    0.07
> (lake, bern)     0.07
> (limmat, bern)   0.07
> (flow, bern)     0.07
> (geneva, bern)   0.07
b) What is the highest posterior probability that you observe and why?
> (bear, bern) with a value of 0.21
c) Why are the prior probabilities all 1/3?
> Because we have for every class one document (zurich, bern, geneva)

Test your classifier with the test document *The name of the city comes from the word 'bear'.* What goes wrong? Can you fix it?

> the word bear is not identified as the word bear but as the word 'bear' with colons. We can fix this and it works

Can you explain the performance of your classifier on the following test corpus?

> the problem is the inverted sentece "There is no lake". MNB only checks for occurences of words and not their deeper meening, this is the reason it has problem with 'not'


Now test your classifier with the one-sentence document "The federal capital is pretty." What happens?

> none of the words is available in the training data. This is why the sentence can not be classified



## Lab b

Something goes wrong. What is it?

> Bears and bear are not lemmatized and this is why they are treated as different words


__YOUR ASSIGNMENT__

- Train a classifier with our extended training data
  - > already done
- Evaluate its performance using all standard metrics
  - > already done
- Print out the confusion matrix
  - > already done
- Examine the test documents that got misclassified
  - > Lake has the highest probability for or geneva according to the training set which was used to train the model. I personally observed with other language models problems with *invertet* sentences.
- Can you explain what is happening? Have we improved the classifier? Why or why not?
  - > We made the classifier aware of more words which doesn't necessarly mean the performance will improve. In my opinion we improved the model but have test-data which is artifically created to *trick* the model.


Bonus question: how was the MNB able to classify *It is the city of Zwingli.*, given that *Zwingli* doesn't appear in the training data?
> The reason is the word *city* which gives the classifier the highes probability to label the sentece with the class 'zurich'

## Lab c
Now run *mnb_tfidf* without removing the stopwords and analyze its performance. Why doesn't the performance drop as much as it did with CountVectorizer?
> I guess TF_IDF already adresses the problem with very common words available in all of the documents as TF_IDF decreases the importance of very common words present along all different kind of documents.

Experiment with other classifiers (other than MNB) from scikit-learn. For instance, try Stochastic Gradient Descent. What's the best performance you can get using the default parametrization of the scikit-learn classifiers?

MultinomialNB: 0.675
DecisionTree: 0.401
RandomForestClassifier: 0.595
KNeighborsClassifier: 0.081
SGDClassifier: Accuracy: 0.713
MLPClassifier: Accuracy: 0.313 - /usr/local/lib/python3.7/dist-packages/sklearn/neural_network/_multilayer_perceptron.py:696: ConvergenceWarning: Stochastic Optimizer: Maximum iterations (200) reached and the optimization hasn't converged yet.
  ConvergenceWarning,