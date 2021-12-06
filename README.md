# NLP based Spell Checker Model
### Instructions to run the model
1. Open the code base in Colab.
2. Execute all the cells one-by-one.
3. Now, you can test the model by custom input/output in the Testing Code cell.

### Methodology
The  model takes a (misspelt) sentence and returns the corrected version of that sentence. Firstly, our model takes the sentence, finds the named entities in that sentence and excludes them from any unnecessary correction. After that, it corrects the tense of the words and scans the sentence for words that are not in the dictionary (set of unique words in the training set) and for each word that is not in the dictionary. Following this we make a candidate list for words that can potentially substitute the incorrect word. Then a suggestion list is prepared and finally the model chooses a word in the suggestion list that has minimal edit distance and has the highest bigram probability. That is the candidate should be selected using the previous and following word in a bigram language model. 
This implementation of our spell-checker is like a dictionary lookup where the model takes the incorrect words in a sentence, finds out its correct form, and replaces it to make the sentence accurate, except for the fact that we are not using a one to one dictionary mapping of incorrect words to correct words. That would be effective, but it is inefficient as we cannot possibly get all words in a language with every wrong permutation of theirs feasibly. Even if we did, it would be a huge dataset and out of the scope of this project. 
Hence we use two major functions - the minimal distance function and the bigram probability function to approximate the correct word from the dictionary for a misspelt word. The edit distance method is built into NLTK. The method calculates how similar two strings are to one another by counting the minimum number of operations required to transform one string into the other.
