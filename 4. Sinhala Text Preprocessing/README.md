[![Previous](https://img.shields.io/badge/previous-green.svg)](https://sinlingua.github.io/documentation/3.%20Sinhala%20Grammar%20Conversion)
[![Home](https://img.shields.io/badge/home-orange.svg)](https://sinlingua.github.io/documentation/)
[![Next](https://img.shields.io/badge/next-blue.svg)](https://sinlingua.github.io/documentation/5.%20Sinhala%20Text%20Summarization)

# Sinhala Text Preprocessing

සිංLingua is an advanced Python library designed to empower Sinhala text analysis by addressing the unique challenges of the language. With a focus on accurate and efficient processing, සිංLingua integrates essential techniques like stemming, stop word handling, and tokenization. Its specialized features enable effective text data cleaning and transformation, crucial for various natural language processing tasks.

## 1. Sinhala text Stemming


```python
from sinhala_data_processor.preprocessor.stemmer import SinhalaStemmer

stemmer_obj = SinhalaStemmer()

input = '...'  # your sentence

output = stemmer_obj.stemmer(input)

print(output)
```

stemmer_obj.stemmer(input)
[![Previous](https://img.shields.io/badge/previous-green.svg)](https://sinlingua.github.io/documentation/3.%20Sinhala%20Grammar%20Conversion)
[![Home](https://img.shields.io/badge/home-orange.svg)](https://sinlingua.github.io/documentation/)
[![Next](https://img.shields.io/badge/next-blue.svg)](https://sinlingua.github.io/documentation/5.%20Sinhala%20Text%20Summarization)
