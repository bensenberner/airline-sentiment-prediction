I classify the sentiment of tweets within [this dataset](https://www.kaggle.com/crowdflower/twitter-airline-sentiment) as `positive`, `neutral`, or `negative` using the fast.ai implementation of [ULMFiT](https://arxiv.org/abs/1801.06146).
1. I perform exploratory data analysis in [this notebook](notebooks/Data.ipynb).
    - Create a train / test set, only looking at the train set for the rest of the project until the very end
    - Determine the distribution of classes
    - Get a sense of the defining characteristics of each class (the topic / tone of tweets of each sentiment)
    - Describe how I augmented the airline dataset with a [different tweet dataset](https://www.kaggle.com/kazanova/sentiment140), making sure to keep the class distributions the same after doing the join
    - Beginning to consider using [yet another tweet dataset](https://www.kaggle.com/c/tweet-sentiment-extraction/discussion/143094)
2. [Create a classifier based on unmodified airline data only](notebooks/Airline.ipynb)
    - Create a language model that can create useful embeddings for tweets
    - Use those embeddings to train a classifier
    - Train another classifier in which I oversample the minority classes in a bid to achieve a higher auc-roc score
3. [Create a classifier based on oversampled airline data](notebooks/Airline_Rebalanced.ipynb)
    - Randomly oversampled the minority classes (positive and neutral) until they both had the same cardinality as the majority class (negative)
    - The hope is that the classifier I create from this new dataset will achieve higher recall on the minority classes since it now has a "better sense" of what they look like, but perhaps at the cost of lower recall on the majority class
    - Trained the classifier exactly as before
4. [Create a classifier based on airline data + sentiment-140 data](notebooks/Airline-and-Sentiment140.ipynb)
    - Create a language model that can represent airline data + sentiment-140 data
    - Train a classifier using only airline data
5. [Evaluate the performance of the best classifiers against the test set](notebooks/Testing.ipynb)
    - Compute the test accuracy of all models, compare it to the baseline
    - Compute the au-roc score
    - Examine the confusion matrix to determine the most common types of mistakes the classifier mistakes
    - Explore those mistakes and try to determine if any meaningful patterns exist
  
------
fast.ai challenge questions:
- Highest test accuracy on this dataset?
  - [81.3](https://www.kaggle.com/jiashenliu/how-can-we-predict-the-sentiment-by-tweets)
  - [77.39](https://www.kaggle.com/bertcarremans/deep-learning-for-sentiment-analysis)
  - My test accuracy is 83.2
- What type of visualization will help me grasp the nature of the problem / data
  - Look at the frequency of words within each sentiment
  - Distribution of "label confidence" for each sentiment
------
TODO:
- Describe why fast.ai's accuracy metrics were confusing
- Wasn't able to achieve reproducible steps in google col