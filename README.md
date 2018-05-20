# Basics of Natural Language Toolkit
The Natural Language Toolkit (NLTK) is a platform used for building Python programs that work with human language data for applying in statistical natural language processing (NLP). 

## Installing NLTK
Simply run the following command
```
sudo pip install -U nltk
```

## Downloading the data
NLTK comes with many corpora, toy grammars, trained models, etc.To download run the following python code.

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
from nltk.tokenize import word_tokenize,sent_tokenize #Importing
example="Hey there I am using NLTK.And it's going great" #Some Random text
print(word_tokenize(example))
print(sen_tokenize(example))
```

