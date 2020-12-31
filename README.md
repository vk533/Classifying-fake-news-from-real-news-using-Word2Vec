# Classifying fake news from real news using Word2Vec
## Need for Word2Vec
Many NLP systems and techniques treat word as atomic units - there is no similarity between the words as these are represented as indices in a vocabulary. Therefore the simple models trained on huge amounts of data outperform complex systems trained on less data. However, simple techniques are at their limits in many tasks. The amount of relevant in-domain data for automatic speech recognition is limited - the performance is usually dominated by the size of high quality transcribed speech data. With the advent of new machine learning techniques in recent years, it has become possible to train more complex models on much larger dataset and they typically outperform the simple models. Probably the most successfull concept is to use distributed representations of words. For example, neural network based language models significantly outperform N-gram models.

## Introduction to Word2Vec
Word2vec is a technique for natural language processing. The word2vec algorithm uses a neural network model to learn word associations from a large corpus of text. Once trained, such a model can detect synonymous words or suggest additional words for a partial sentence. As the name implies, word2vec represents each distinct word with a particular list of numbers called a vector. The vectors are chosen carefully such that a simple mathematical function (the cosine similarity between the vectors) indicates the level of semantic similarity between the words represented by those vectors.

Word2vec is a group of related models that are used to produce word embeddings. These models are shallow, two-layer neural networks that are trained to reconstruct linguistic contexts of words. Word2vec takes as its input a large corpus of text and produces a vector space, typically of several hundred dimensions, with each unique word in the corpus being assigned a corresponding vector in the space. Word vectors are positioned in the vector space such that words that share common contexts in the corpus are located close to one another in the space.

## One-Hot Encoding
One-hot encoding is used in machine learning as a method to quantify categorical data. In short, this method produces a vector with length equal to the number of categories in the data set.  If a data point belongs to the

ith category then components of this vector are assigned the value 0 except for the ith component, which is assigned a value of 1.  In this way one can keep track of the categories in a numerically meaningful way.
 
The question may arise: What happens if there are multiple 1’s? Which classification is correct? This is quickly rectified by the fact that something that is one-hot encoded has exactly one position in its array that is labeled as a 1. For example, [0,0,0,1,0] would be a valid one-hot encoding that would tell you the classification in position 4 (or 3 in array indexing) is the classification of the object. Contrastingly, [0,1,0,1,0],and [1,1,1,1,1] are examples of invalid one-hot encodings.

Consider the problem of classifying a person into one of four categories: male, female, gender-neutral, and other. We can represent this as an array with four positions. For every person we encounter, we want to be able to represent them as a one-hot encoding with relation to our four categories. Let’s say walking down the street, we encounter 4 people who identify as female, 3 people who identify as male, one person who identifies as gender-neutral, and 2 people who identify as something other than the other three categories. Then, we can represent these people in the following way:
 
 - [0,1,0,0] // female
 - [0,1,0,0]
 - [0,1,0,0]
 - [0,1,0,0]
 - [1,0,0,0] // male
 - [1,0,0,0]
 - [1,0,0,0]
 - [0,0,1,0] // gender-neutral
 - [0,0,0,1] // other
 - [0,0,0,1]
 
Notice how the order of the categories as they were presented remained the same. It is important that one establish the proper order of the array before something can be properly encoded. For this example, we maintained the order that the categories were initially given, meaning that our template array looked like [male, female, gender-neutral, other].
