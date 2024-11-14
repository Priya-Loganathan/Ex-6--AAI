# EX-06 Implementation of Semantic Analysis

# Aim: 
To perform Parts of speech identification and Synonym using Natural Language Processing (NLP) techniques. 

# Algorithm:
Step 1: Import the nltk library.
Step 2: Download the 'punkt', 'wordnet', and 'averaged_perceptron_tagger' resources.
Step 3:Accept user input for the text.
Step 4:Tokenize the input text into words using the word_tokenize function.
Step 5:Iterate through each word in the tokenized text.
•	Perform part-of-speech tagging on the tokenized words using nltk.pos_tag.
•	Print each word along with its corresponding part-of-speech tag.
•	For each verb , iterate through its synsets (sets of synonyms) using wordnet.synsets(word).
•	Extract synonyms and antonyms using lemma.name() and lemma.antonyms()[0].name() respectively.
•	Print the unique sets of synonyms and antonyms.

# Program:

## Developed By: ANBUSELVAM A
## REGISTER NO: 212222240009

## Importing NLTK and Resource Downloads
```
import nltk
nltk.download( 'punkt' )
nltk.download('wordnet')
nltk.download('omw-1.4')
from nltk.tokenize import word_tokenize
nltk.download( 'averaged_perceptron_tagger' )
from nltk.corpus import wordnet
```
## Tokenization and Part-of-Speech Tagging
```
sentence=input()
words = word_tokenize(sentence)
pos_tags= nltk.pos_tag(words)
for word, tag in pos_tags:
    print(f"{word:<6} - {tag}")
```
## Extracting Synonyms and Antonyms from Words
```
synonyms =[]
antonyms =[]
for word in words:
    for syn in wordnet.synsets(word):
        for lemma in syn.lemmas():
            synonyms.append (lemma.name())
            if lemma.antonyms():
                antonyms.append (lemma.antonyms()[0].name())
print ( "Synonyms : " ,set(synonyms))
print ( "Antonyms : " ,set(antonyms))
```

# Output:
## Parts of Speech:
![image](https://github.com/user-attachments/assets/d893a061-b5aa-4075-8b80-4552c587956d)

## Synonyms and Antonyms:
![image](https://github.com/user-attachments/assets/3a0ca3c3-92fe-4c88-843f-6a9efd919d5f)


# Result:
Thus ,the program to perform the Parts of Speech identification and Synonymis executed sucessfully.
