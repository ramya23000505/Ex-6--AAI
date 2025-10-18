<H3>NAME: RAMYA R</H3>
<H3>REGISTER NO: 212223230169</H3>
<H3>EX. NO.6</H3>
<H3>DATE:</H3>
<H1 ALIGN =CENTER>Implementation of Semantic ANalysis</H1>
<H3>Aim: to perform Parts of speech identification and Synonym using Natural Language Processing (NLP) techniques. </H3> 
 <BR>
<h3>Algorithm:</h3>
Step 1: Import the nltk library.<br>
Step 2: Download the 'punkt', 'wordnet', and 'averaged_perceptron_tagger' resources.<br>
Step 3:Accept user input for the text.<br>
Step 4:Tokenize the input text into words using the word_tokenize function.<br>
Step 5:Iterate through each word in the tokenized text.<br>
•	Perform part-of-speech tagging on the tokenized words using nltk.pos_tag.<br>
•	Print each word along with its corresponding part-of-speech tag.<br>
•	For each verb , iterate through its synsets (sets of synonyms) using wordnet.synsets(word).<br>
•	Extract synonyms and antonyms using lemma.name() and lemma.antonyms()[0].name() respectively.<br>
•	Print the unique sets of synonyms and antonyms.
<H3>Program:</H3>
```py
import nltk
from nltk.corpus import wordnet
from nltk.tokenize import word_tokenize

# Download necessary data
nltk.download('punkt')
nltk.download('averaged_perceptron_tagger')
nltk.download('wordnet')

# Input sentence
sentence = input()

# Display input
print("\n Sentence:")
print(sentence)

# Tokenize and tag parts of speech
words = word_tokenize(sentence)
pos_tags = nltk.pos_tag(words)

# Display POS tagging
print("\n POS Tags:")
for word, tag in pos_tags:
    print(f"{word:10} {tag}")

# Find synonyms and antonyms
synonyms = []
antonyms = []

for word in words:
    for syn in wordnet.synsets(word):
        for lemma in syn.lemmas():
            synonyms.append(lemma.name())
            if lemma.antonyms():
                antonyms.append(lemma.antonyms()[0].name())

# Display synonyms and antonyms
print("\nSynonyms :", set(synonyms))
print("  Antonyms :", set(antonyms))


<H3>Output</H3>

<img width="469" height="61" alt="image" src="https://github.com/user-attachments/assets/b7e97375-1f03-4948-8ab9-1c5ef024a224" />
<img width="319" height="254" alt="image" src="https://github.com/user-attachments/assets/516e1e13-33c0-4b92-9d4a-c63dbfbafa51" />
<img width="1622" height="29" alt="image" src="https://github.com/user-attachments/assets/7606395f-4728-46a7-b37b-886dd4c7687c" />
<img width="640" height="30" alt="image" src="https://github.com/user-attachments/assets/8c50af1f-7a1a-4c9b-9bf6-63958e4cfa0b" />


<H3>Result:</H3>
Thus ,the program to perform the Parts of Speech identification and Synonymis executed sucessfully.
