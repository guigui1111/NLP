# Gensim
Definition: Uses top academic models to perform complex tasks <br>
Examples: Building document or word vectors (word embedding: is trained from a large corpus and a multi-dimental representation of word or document. We can see relationships among words.)
      <br> LDA (Latent Dirichlet allocation) visualization. 
      <br>Performing topic identification and document comparison
      
## Gensim pipeline:
my_doc(list of strs) -> tokens -> Gensim Dictionary (token ids, for checking, see token2id attributes) -> create Gensim corpus (list of lists, each list is a doc, each doc is a series of tuples with first number to be token id and second number to be frequency)



# Creating and querying a corpus with gensim
###### Import Dictionary
from gensim.corpora.dictionary import Dictionary

###### Create a Dictionary from the articles: dictionary
dictionary = Dictionary(articles)

###### Select the id for "computer": computer_id
computer_id = dictionary.token2id.get("computer")

###### Use computer_id with the dictionary to print the word
print(dictionary.get(computer_id))

###### Create a MmCorpus: corpus
corpus = [dictionary.doc2bow(article) for article in articles]

###### Print the first 10 word ids with their frequency counts from the fifth document
print(corpus[4][:10])
