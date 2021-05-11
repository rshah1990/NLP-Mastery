# Word2vec

- Continuous Bag-of-Words Model: predicts the middle word based on surrounding context words. several times faster to train than the skip-gram, slightly better accuracy for the frequent words.
- Continuous Skip-gram Model: predict words within a certain range (window size) before and after the current word in the same sentence.works well with a small amount of the training data, represents well even rare words or phrases.

| Sentence  | Window Size | skip-gram |
| ------------- | ------------- | ------------- |
| I am rohit shah & machine learning developer | 1  | (rohit,shah);(rohit,am) |

- Problems With CBoW/Skip-gram :  the calculation of the final probabilities using the softmax is quite an expensive operation & only the weights corresponding to the target word might get a significant update
- Negative Sampling: Negative sampling allows us to only modify a small percentage of the weights, rather than all of them for each training sample
- Sub Sampling: In sub-sampling, we limit the number of samples for a word by capping their frequency of occurrence. For frequently occurring words, we remove a few of their instances both as a neighboring word and as the input word.


| word1  | word2 | Target |
| ------------- | ------------- | ------------- |
| Rohit | shah  | 1 |
| Rohit | am  | 1 |
| Rohit | developer  | 0 |
| Rohit | learning  | 0 |


# FastText

- Logic is very similar to word2vec model
- word -> subword info -> n-gram -> embedding for n-gram
- word embedding is avarage of n-gram embeddings 
- The main advantage of FastText embeddings over Word2Vec is to take into account the internal structure of words while learning word representations, which could be very useful for morphologically rich languages, and also for words that occur rarely
- It can take care of spelling mistakes as well

# Poincare Embeddings
