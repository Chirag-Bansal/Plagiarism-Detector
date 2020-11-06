# Plagiarism-Detector

The aim of the assignment was to create a plagirism detector in C

## Introcuction to N-grams
A concept widely used in natural language processing, word N-grams are essentially "phrases" of length
N in a given text, for our purposes. Their main importance is in the fact that they can represent Markov
chains of length N, which allows for a simple representation of phrases which is also natural fit for languages
like English, because the main structures that stand out in a text are linear owing to the low nesting-levels
in most languages. Their relevance to our use-case is that in a plagiarized document, the frequency of any
particular phrase should be heuristically similar to that in the document where it was plagiarized from.

##High-level Description of the Algorithm

From any given text, we nd the sorted array containing all possible 3-gram hashes in the text. To nd the
similarity between the texts, we extract frequency vectors of 3-grams corresponding to both texts, sorted
according to 3-gram hashes in both the texts (and if a hash is not found in one le, we simply assign the
value 0 to the frequency of that hash), and nd the cosine similarity between any two such vectors.
