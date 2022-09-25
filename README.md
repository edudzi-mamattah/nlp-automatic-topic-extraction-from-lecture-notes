# Automatic Topic Extraction from Taught Lectures using Natural Language Processing 

*Project Duration: May 2022 - September 2022*


A project conducted to research different state-of-the-art methods of parsing text within .pdf files of lecture notes in order to perform automatic topic extraction of the topics within the lecture notes.



•	Extracted text from within .pdf files of lecture notes and concatenated all the text from within one file into a string within a list. Each list contained the lecture notes from one module. There were six modules in total that were worked on.
•	Cleaning of the dataset commenced with removal of characters from the lists of strings that were not alphabets, newline characters, or space characters. This meant that web addresses, email addresses and dates, currency, and other numerals were cleaned from the dataset as they were not required to accomplish the goal of the project.

•	A set of words such as lecturer names, school names, etc. were added to the NLTK set of stopwords; after which those words were removed from the dataset. Then tokenization, followed by lemmatization, were conducted for the dataset.
•	Various representation methods were used to transform the data, namely: bag-of-words, bigrams, trigrams, word2vec, and TF-IDF.

•	Word frequency diagrams, bigram and trigram network diagrams and word clouds were used as exploratory data analysis visualisations to gain insight into the data.

•	Following the above processes, the main algorithms researched into were applied to the data. LDA, TextRank, RAKE, YAKE, and KeyBERT were all ran on the dataset to achieve the goal of topic extraction – and to evaluate their efficacy at accomplishing the task.

•	The implementation revealed that incorporating transformer pre-trained models (KeyBERT) to carry out topic extraction tasks would provide more benefit to the task than completely unsupervised approaches. The semantic and contextual knowledge of language that is retained by such models makes their impact hard to ignore. 

•	Graph-based ranking algorithms (YAKE and RAKE) also have a substantial performance but lacking that context-specific knowledge means that they are sometimes difficult to interpret and simply have too many options for their output. 

•	From the implementation, it was observed that LDA’s method generates a sparse choice of topics from the corpus, yet it fails to capture important words within text. TextRank outputs the list of keywords, but some keywords were surprising as they did not provide any idea as to the topic at hand. 


