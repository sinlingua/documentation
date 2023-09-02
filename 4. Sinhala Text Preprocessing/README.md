[![Previous](https://img.shields.io/badge/previous-green.svg)](https://sinlingua.github.io/documentation/3.%20Sinhala%20Grammar%20Conversion)
[![Home](https://img.shields.io/badge/home-orange.svg)](https://sinlingua.github.io/documentation/)
[![Next](https://img.shields.io/badge/next-blue.svg)](https://sinlingua.github.io/documentation/5.%20Sinhala%20Text%20Summarization)

# Sinhala Text Preprocessing

සිංLingua is an advanced Python library designed to empower Sinhala text analysis by addressing the unique challenges of the language. With a focus on accurate and efficient processing, සිංLingua integrates essential techniques like stemming, stop word handling, and tokenization. Its specialized features enable effective text data cleaning and transformation, crucial for various natural language processing tasks.

## 1. Sinhala text Stemming

The SinhalaStemmer class, an integral component of the Sinlingua library, is devised to elevate the accuracy and efficiency of Sinhala text preprocessing through a systematic four-step stemming process. Each procedure is meticulously crafted to address different aspects of stemming intricacies within the Sinhala language.
- Stem Dictionary Lookup (Step One)
- Suffix Removal (Step Two)
- Inner Suffix Handling (Step Three)
- Dependent Vowel Suffix Removal (Step Four)

```python
from sinhala_data_processor.preprocessor.stemmer import SinhalaStemmer

stemmer_obj = SinhalaStemmer()

input = '...'  # your sentence

output = stemmer_obj.stemmer(input)

print(output)
```
## 2. Sinhala stopword handling

Words, such as "සහ" (and), "සමග" (with), and "ලෙස" (like), are part of a predefined list of stop words. The primary goal of this process is to eliminate words that add minimal semantic value to the text while focusing on the meaningful content.


```python
from sinlingua.preprocessor.stopword_remover import StopWordRemover


input = '...'  # your sentence

stopword_remover = StopWordRemover()

remaining_words = stopword_remover.remove_stop_words(input)

print(remaining_words)
```

## 3. Sinhala text Tokenization

Tokenization is a foundational process in Sinhala text preprocessing that involves breaking down a continuous stream of text into individual units known as tokens. These tokens typically correspond to words or subwords, and they serve as the building blocks for subsequent linguistic analysis and processing


```python
from sinlingua.preprocessor.tokenizer import SinhalaTokenizer


input = '...'  # your sentence

tokenizer = SinhalaTokenizer()

tokenz = tokenizer.tokenize(input)

print(tokenz)

```

## Getting Started

To use the Sinhala Text preprocessing component of සිංLingua, follow these steps:

1. Install the සිංLingua library:
   ```bash
   pip install sinlingua
   ```

2. Import the required classes for the chosen preprocessing approach:
   ```python
   
   from sinlingua.preprocessor.tokenizer import SinhalaTokenizer
   from sinlingua.preprocessor.stopword_remover import StopWordRemover
   from sinlingua.preprocessor.stemmer import SinhalaStemmer
   
   ```

3. Initialize the preprocessor class based on your chosen approach:
   
   ```python
   
   stemmer_obj = SinhalaStemmer() # For Stemming
   stopword_remover = StopWordRemover() # For removing stopwords
   tokenizer = SinhalaTokenizer() # For tokenize a given paragraph into tokens
   
   ```

4. Use the functions of the above mentioned classes accordingly

[![Previous](https://img.shields.io/badge/previous-green.svg)](https://sinlingua.github.io/documentation/3.%20Sinhala%20Grammar%20Conversion)
[![Home](https://img.shields.io/badge/home-orange.svg)](https://sinlingua.github.io/documentation/)
[![Next](https://img.shields.io/badge/next-blue.svg)](https://sinlingua.github.io/documentation/5.%20Sinhala%20Text%20Summarization)
