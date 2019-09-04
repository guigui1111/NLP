###### Import necessary modules
from nltk.tokenize import sent_tokenize<br>from nltk.tokenize import word_tokenize

###### Split scene_one into sentences: sentences
sentences = sent_tokenize(scene_one)

###### Use word_tokenize to tokenize the fourth sentence: tokenized_sent
tokenized_sent = word_tokenize(sentences[3])

###### Make a set of unique tokens in the entire scene: unique_tokens
unique_tokens = set(word_tokenize(scene_one))

###### Print the unique tokens result
print(unique_tokens)


###### Search for the first occurrence of "coconuts" in scene_one: match
match = re.search("coconuts", scene_one)

###### Print the start and end indexes of match
print(match.start(), match.end())

###### Write a regular expression to search for anything in square brackets: pattern1
pattern1 = r"\[.*\]"

###### Use re.search to find the first text in square brackets
print(re.search(pattern1, scene_one))

###### Find the script notation at the beginning of the fourth sentence and print it
pattern2 = r"[\w\s]+:"<br>print(re.match(pattern2, sentences[3]))

# Regex with NLTK tokenization

###### Import the necessary modules
from nltk.tokenize import regexp_tokenize
from nltk.tokenize import TweetTokenizer

###### Define a regex pattern to find hashtags: pattern1
pattern1 = r"#\w+"

###### Use the pattern on the first tweet in the tweets list
regexp_tokenize(tweets[0], pattern1)

###### Write a pattern that matches both mentions and hashtags
pattern2 = r"([@#]\w+)"

###### Use the pattern on the last tweet in the tweets list
regexp_tokenize(tweets[-1], pattern2)

###### Use the TweetTokenizer to tokenize all tweets into one list
tknzr = TweetTokenizer()<br>all_tokens = [tknzr.tokenize(t) for t in tweets]<br>print(all_tokens)

# Building a Counter with bag-of-words
###### Import Counter
from collections import Counter

###### Tokenize the article: tokens
tokens = word_tokenize(article)

###### Convert the tokens into lowercase: lower_tokens
lower_tokens = [t.lower() for t in tokens]

###### Create a Counter with the lowercase tokens: bow_simple
bow_simple = Counter(lower_tokens)

###### Print the 10 most common tokens
print(bow_simple.most_common(10))

# Text preprocessing with Python
from ntlk.corpus import stopwords
###### Import WordNetLemmatizer
from nltk.stem import WordNetLemmatizer

###### Retain alphabetic words: alpha_only
alpha_only = [t for t in lower_tokens if t.isalpha()]

###### Remove all stop words: no_stops
no_stops = [t for t in alpha_only if t not in english_stops]

###### Instantiate the WordNetLemmatizer
wordnet_lemmatizer = WordNetLemmatizer()

###### Lemmatize all tokens into a new list: lemmatized
lemmatized = [wordnet_lemmatizer.lemmatize(t) for t in no_stops]

###### Create the bag-of-words: bow
bow = Counter(lemmatized)

###### Print the 10 most common tokens
print(bow.most_common(10))
