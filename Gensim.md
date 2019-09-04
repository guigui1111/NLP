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

# Gensim bag-of-words
######  Save the fifth document: doc
doc = corpus[4]
######  Sort the doc for frequency: bow_doc
bow_doc = sorted(doc, key=lambda w: w[1], reverse=True)

######  Print the top 5 words of the document alongside the count
for word_id, word_count in bow_doc[:5]:
<br>   print(dictionary.get(word_id), word_count)
    
######  Create the defaultdict: total_word_count
total_word_count = defaultdict(int)
for word_id, word_count in itertools.chain.from_iterable(corpus):
<br> total_word_count[word_id] += word_count

######  Create a sorted list from the defaultdict: sorted_word_count 
sorted_word_count = sorted(total_word_count.items(), key=lambda w: w[1], reverse=True) 

######  Print the top 5 words across all documents alongside the count
for word_id, word_count in sorted_word_count[:5]:
<br>  print(dictionary.get(word_id), word_count)


# Tf-idf (term frequency–inverse document frequency) with gensim
###### Import TfidfModel
from gensim.models.tfidfmodel import TfidfModel

###### Create a new TfidfModel using the corpus: tfidf
tfidf = TfidfModel(corpus)

###### Calculate the tfidf weights of doc: tfidf_weights
tfidf_weights = tfidf[doc]

###### Print the first five weights
print(tfidf_weights[:5])

###### Sort the weights from highest to lowest: sorted_tfidf_weights
sorted_tfidf_weights = sorted(tfidf_weights, key=lambda w: w[1], reverse=True)

###### Print the top 5 weighted words
for term_id, weight in sorted_tfidf_weights[:5]:
<br>  print(dictionary.get(term_id), weight)

# LDA (Latent Dirichlet allocation)
