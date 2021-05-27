# Universal Healthcare Discussions NLP

## Abstract
The goal of this project was to use natural language processing techniques to craft a topic model, delineating subtopics of discussion surrounding universal healthcare on twitter. I worked with twitter data gathered through python's tweet gathering package, [twint](https://pypi.org/project/twint/) to identify a  list of 7 subtopics that are the main categories of conversation surrounding universal healthcare. After refining an interpretted topic model, I performed sentiment analysis on each of the topics from the topic model to analyse what subtopics might be more contentious and should be approached with more caution/analysis/thoughtfulness. 

## Design
This project was designed according to a generic NLP workflow. One data was gathered, preprocessed, and further explored, it was vectorized and topic modeling was initiated, followed by sentiment analysis. The topic model have potential as a research outline for universal healthcare campaigns.  Campaigns aiming to morph conversations surrounding universal healthcare, can use this topic model to initiate growing an understanding of hestitations against universal healthcare so they may better craft rebuttals against the hesitations. 


## Data
The dataset contains 26,457 tweets. All the tweets were pulled using twint, a twitter data gathering python package. The search queries were "universal healthcare","affordable healthcare", and "healthcare", all of which were removed as stopwords before topic modeling. 

### Breakdown of Code Notebooks:
- [This Notebook](https://github.com/mehiks11/Universal_Healthcare_NLP/blob/master/Code/Data%20Pulling%20(1).ipynb) contains code for pulling data using twint.
- [This Notebook](https://github.com/mehiks11/Universal_Healthcare_NLP/blob/master/Code/Data%20Cleaning%20(1).ipynb) contains code for data cleaning.
- [This Notebook](https://github.com/mehiks11/Universal_Healthcare_NLP/blob/master/Code/Modeling%20(1)%20-%20Initial%20Topic%20Modeling.ipynb) contains code for Topic Modeling.
- [This Notebook](https://github.com/mehiks11/Universal_Healthcare_NLP/blob/master/Code/Modeling%20(2)%20-Sentiment%20Analysis.ipynb) contains code for whole data sentiment analysis.
- [This Notebook](https://github.com/mehiks11/Universal_Healthcare_NLP/blob/master/Code/Modeling%20(3)%20-%20Topic%20Modeling%20by%20Sentiment%20Analyzed%20Groups.ipynb) contains code for sentiment analysis by topic.


## Algorithms

*Data Preprocessing*
1. Cleaning out all URLs and emojis from tweets//formatting (lowercasing, etc.)
2. Using spaCy to remove stopwords while tokenizing
3. Lemmatizing tweets 

*Vectorization & Topic Modeling*
1. Document term matrix with tfidf vectorizer
2. Fitting NMF model with 5 components
3. Interpretting 5 topics 
The topic modeling portion involved iteratively testing various numbers of components and deciding on 5 according to highest coherence in most frequent words in each topic, and some subjective interpretability comparisons. 

**Final Topics Yielded from Topic Model**
1. Political
2. Human Rights
3. Quality of Life
4. Infrastrucutre
5. Comparisons to other countries
6. Public Services
7. Accessibility

*Sentiment Analysis*
1. Sentiment analysis on whole dataset
2. Sentiment analysis by topic

Every topic had a higher percentage of tweets labelled as "positive". Though sentiment analysis is still a fairly flawed process, ranking the percentages within each topic might help to guide further exploration. 

Most to Least Positive sentimented:
1. Quality of Life
2. Public Service/Accessibility
3. Infrastructure
4. Political/Human Rights
5. Comparisons to other countries

Most to Least Negative sentimented:
1. Political/Human Rights
2. Comparisons to other countries
3. Infrastructure
4. Public Service/Accessibility
5. Quality of Life

## Tools
- pandas
- twint for data gathering
- spacy for text preprocessing
- sklearn for topic modeling
- sklearn sentiment vader

## Communication
There are [slides](https://github.com/mehiks11/Universal_Healthcare_NLP/blob/master/Deliverables/Universal%20Healthcare%20NLP%20ppt.pdf) accompanying the notebooks of code that outline the process/workflow of the entire project. 
