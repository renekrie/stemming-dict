stemming-dict
=============


Format: Each entry of the dictionary consists of two words that are assumed to share a common stem. An entry is just a line in the dictionary file consisting of  the two words separated by a comma. 

    <word1>,<word2>

You can use this format as an input for the Solr SynonymFilter. All words have been lower-cased and hyphens have been removed.

The entries were derived from a corpus analysis (approx. 700m tokens) as follows:

1. Find all pairs of words in the corpus that share a common stem in the Porter Stemmer algorithm for German
2. Compare all the environments in which the two words occur in the corpus and calculate a similarity (between 0.0 and 1.0)
3. Assume that the two words should have the same stem if their similarity is above a given threshold.

The environment is defined by a window of 40 words to each side of the occurence of a word - omitting stopwords, numbers and words that occur less then 40 times in the corpus.
The similarity was then calculated as a cosine between vectors, which where created using 'random indexing' of the environments.

The dictionary is only available for German so far. It consists of files that each represent a different minimum threshold for similarity (for example stemming-dict-de-0.25 has a minimum similarity of 0.25 and stemming-dict-de-0.175 a minimum similarity of 0.175).

This dataset is licensed under a Creative Commons Attribution-ShareAlike 3.0 Unported License (see [http://creativecommons.org/licenses/by-sa/3.0/]([http://creativecommons.org/licenses/by-sa/3.0/]))

Copyright (c) 2012/2013 by René Kriegler (post@rene-kriegler.de)

 


 
 