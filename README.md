# Basics of Natural Language Toolkit
The Natural Language Toolkit (NLTK) is a platform used for building Python programs that work with human language data for applying in statistical natural language processing (NLP). 

## Installing NLTK
Simply run the following command
```
sudo pip install -U nltk
```

## Downloading the data
NLTK comes with many corpora(Paragraph of text), toy grammars, trained models, etc.To download run the following python code.

```
import nltk
nltk.download()
```

A new window should open, showing the NLTK Downloader.Select All packages and hit the download button.
The download will take time as per your internet speed.Let the download complete than follow.

## Learning NLTK
So you are now all set to use NLTK.

### Word and Sentence tokenizing
What we do here is split sentences and words from the body of text.
> Token - Each "entity" that is a part of whatever was split up based on rules. For example word is a token when we use word_tokenize.
Let's write some quick code to see how its done
```
from nltk.tokenize import word_tokenize,sent_tokenize           #Importing
example="Hey there I am using NLTK. And it's going great"       #Some Random text
print(word_tokenize(example))                                   #Split into
print(sent_tokenize(example))                                   #Split into sentences
```
**OUTPUT**
```
['Hey', 'there', 'I', 'am', 'using', 'NLTK', '.', 'And', 'it', "'s", 'going', 'great']
['Hey there I am using NLTK.', "And it's going great"]
```
Notice that punctuation is treated as a separate token. Also, notice the separation of the word **it's** into **it** and **'s**. 
So you might think that Hey I can do this without NLTK then why should I use NLTK, well yes you maybe able to do this without NLTK but there will be many exceptions and would require quite a little time.

### Stop Words
We know that some words carry more meaning than other words.We can also see that some words are just plain useless, and are filler words ,we just use these word so that the sentence doesnt't sound strange.We would not want these words taking up space in our database, or taking up valuable processing time. As such, we call these words "stop words" because they are useless, and we wish to do nothing with them.

> NLTK provides us with a list of words that they consider stop words.

Let's write some quick code to see how it's done
```
from nltk.corpus import stopwords
from nltk.tokenize import word_tokenize

test_sentence= "I am trying to show stop word filtration"

stop_words=set(stopwords.words("english"))            #Set of stop words NLTK provides us with
words = word_tokenize(test_sentence)                  #Splitting into words

filtered=[]

for w in words:                                       #Iterate through all the words         
	if w not in stop_words:                           #If the word is not a stop word , append it in filtered
		filtered.append(w)


print(filtered)
```
**OUTPUT**
```
['I', 'trying', 'show', 'stop', 'word', 'filtration']
```

### Stemming words with NLTK
Stemming is the process for reducing inflected words to their word stem (base form).A single word can appear in many variations.
Consider the following :

> The stem word of  **waited , waiting , waits** is **wait**. So what we are gonna do is normalize words to its base form.

One of the most common stemming algorithms is the Porter stemming algorithm by Martin Porter. 
Let's write some code using it

```
from nltk.stem import PorterStemmer                    #Import PorterStemmer
ps = PorterStemmer()

example_words=["game","gaming","gamed","games"]        #Example words      

for w in example_words:                                #Iterate through them and stem
	print(ps.stem(w))
```

**OUTPUT**
game
game
game
game

Isn't it cool?

### Part of Speech Tagging 