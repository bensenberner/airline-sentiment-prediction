I classify the sentiment of tweets within [this dataset](https://www.kaggle.com/crowdflower/twitter-airline-sentiment) as `positive`, `neutral`, or `negative` using the fast.ai implementation of [ULMFiT](https://arxiv.org/abs/1801.06146).
1. I perform exploratory data analysis in [this notebook](Initial.ipynb) (TODO: better link).
  - Create a train / test set, only looking at the train set for the rest of the project until the very end
  - Determine the distribution of classes
  - Get a sense of the defining characteristics of each class (the topic / tone of tweets of each sentiment)
  - Describe how I augmented the airline dataset with a [different tweet dataset](https://www.kaggle.com/kazanova/sentiment140), making sure to keep the class distributions the same after doing the join
  - Beginning to consider using [yet another tweet dataset](https://www.kaggle.com/c/tweet-sentiment-extraction/discussion/143094)
2. Creating a classifier based on the airline data alone (TODO: link)
  - Create a language model that can create useful embeddings for tweets
  - Use those embeddings to train a classifier
3. Creating a classifier based on airline data + sentiment-140 data (TODO: link)
  - Create a language model that can represent airline data + sentiment-140 data
  - Train a classifier using only airline data
4. Evaluate the performance of the best classifiers against the test set (TODO: link)
  - Compute the test accuracy (83.2%), compare it to the baseline
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
TODO: Describe why fast.ai's accuracy metrics were  confusing