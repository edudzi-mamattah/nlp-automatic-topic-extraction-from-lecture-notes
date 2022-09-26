# Automatic Topic Extraction from Taught Lectures using Natural Language Processing 

*Project Duration: May 2022 - September 2022*


A project conducted to research different state-of-the-art methods of parsing text within .pdf files of lecture notes in order to perform automatic topic extraction of the topics within the lecture notes.


## Data Description, Preparation, & Cleaning

### Description

Data used consisted of the leture notes (in pdf presentation formats) of 6 modules (52 lecture notes in total) from <a href= "brunel.ac.uk"> Brunel University </a>. Please note that this data is not included in the repository as I am not allowed to share it publicly.

### Cleaning & Processing

The text from within each of these .pdf files was read into the programming environment as a string, and then appended to a list which consisted of other strings corresponding to other lectures within the same module.
This meant there were 6 lists in total, which had elements which corresponded to a lecture within that module.

Cleaning of the dataset commenced with removal of characters from the lists of strings that were not alphabets, newline characters, or space characters. This meant that web addresses, email addresses and dates, currency, and other numerals were cleaned from the dataset as they were not required to accomplish the goal of the project.

A set of words such as lecturer names, school names, etc. were added to the NLTK set of stopwords; after which those words were removed from the dataset. Then tokenization, followed by lemmatization, were conducted for the dataset.

Various representation methods were then used to transform the data, namely: bag-of-words, bigrams, trigrams, word2vec, and TF-IDF.

## Exploratory Data Analysis 

Word frequency diagrams, bigram and trigram network diagrams, and word clouds were used as exploratory data analysis visualisations to gain insight into the data.

![Word-Frequency-Diagram](https://github.com/edudzi-mamattah/nlp-automatic-topic-extraction-from-lecture-notes/blob/main/Images/FullWordFreq.png) Word Frequency Diagram
![Bigram-Network](https://github.com/edudzi-mamattah/nlp-automatic-topic-extraction-from-lecture-notes/blob/main/Images/FullWordNet.png) Bigram Network Diagram
![Trigram-Network](https://github.com/edudzi-mamattah/nlp-automatic-topic-extraction-from-lecture-notes/blob/main/Images/FullTriNet.png) Trigram Network Diagram

NB: The bigram and trigram nodes that connect to themselves happen because the stopwords linking those word were removed during cleaning, hence, multiple instances of words occurred together enough times to be noticed by the network co-occurrence algorithms.
![Word-Cloud](https://github.com/edudzi-mamattah/nlp-automatic-topic-extraction-from-lecture-notes/blob/main/Images/CombinedWC.png) Word Cloud

## Methodology 

Following the above processes, the main algorithms researched into were applied to the data. 
<a href= "https://www.jmlr.org/papers/volume3/blei03a/blei03a.pdf?ref=https://githubhelp.com"> Latent Dirichlet Allocation</a>, <a href= "https://aclanthology.org/W04-3252.pdf">TextRank</a>, <a href= "https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.657.8134&rep=rep1&type=pdf">RAKE</a>, <a href= "https://www.sciencedirect.com/science/article/pii/S0020025519308588?casa_token=MRjzRkVknWkAAAAA:Z2-1WE-6UnsNbS-dYJjxeq76pfdjk61l41jXpbDOOhNykz5kKFdFv6IEK4l846MUjTL_oHj4L4k">YAKE</a>, and <a href= "https://maartengr. github. io/KeyBERT/index. html"> KeyBERT</a> were all applied to the dataset to achieve the goal of topic extraction – and to evaluate their efficacy at accomplishing the task.

•	The implementation revealed that incorporating transformer pre-trained models (KeyBERT) to carry out topic extraction tasks would provide more benefit to the task than completely unsupervised approaches. The semantic and contextual knowledge of language that is retained by such models makes their impact hard to ignore. 

•	Graph-based ranking algorithms (YAKE and RAKE) also have a substantial performance but lacking that context-specific knowledge means that they are sometimes difficult to interpret and simply have too many options for their output. 

•	From the implementation, it was observed that LDA’s method generates a sparse choice of topics from the corpus, yet it fails to capture important words within text. TextRank outputs the list of keywords, but some keywords were surprising as they did not provide any idea as to the topic at hand. 


