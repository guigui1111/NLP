# NLP includes:
  Topic identification<br>Text classification

# NLP applications include:
  Chatbots<br>Translation<br>Sentiment analysis
  
# Text preprocessing

# Tokenization:
  Turning a string or document into tokens (smaller chunks)<br>One step in preparing a text for NLP<br>Many different theories and rules
<br>
You can create your own rules using regular expressions
  
  Examples:
  
  Breaking out words or sentences\\\Separating punctuation\\\Separating all hashtags in a tweet
  
# Stemming and lemmatization

# Useful library:
## nltk: natural language toolkit
<br>
word_tokenize\\\sent_tokenize\\\regexp_tokenize\\\TweetTokenizer
  
## Gensim
Definition: Uses top academic models to perform complex tasks <br>
Examples: Building document or word vectors (word embedding: is trained from a large corpus and a multi-dimental representation of word or document. We can see relationships among words.)
      <br> LDA (Latent Dirichlet allocation) visualization. 
      <br>Performing topic identification and document comparison
      
### Gensim pipeline:
my_doc(list of strs) -> tokens -> Gensim Dictionary (token ids, for checking, see token2id attributes) -> create Gensim corpus (list of lists, each list is a doc, each doc is a series of tuples with first number to be token id and second number to be frequency)
      

